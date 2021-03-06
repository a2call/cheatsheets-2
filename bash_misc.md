### Bash misc

Compress file or folder to file.tar.gz
```
tar -czf file.tar.gz directory/
tar -czf file.tar.gz file.txt
```

Tar without compression
```
tar -cf file.tar.gz directory/
```

Uncompress TAR and BZ files
```
tar xzf file.tar.gz
tar xjf file.tar.bz2
```

ZIP compress
```
zip -r file.zip folder
```

ZIP Uncompress
```
unzip file.zip
```

ZIP without OS X Files
```
zip -r -X file.zip folder
```

Remove a folder
```
rm -rf folder/
```

Copy folder A to folder B
```
cp -R -p /FolderA/* /FolderB
```

Move from current folder to parent folder
```
cd path/to/folder
mv * ../
```

Change file date
```
touch -t 201306141200 
```

Download a file on Linux and OS X
```
wget http://example.com/file.txt
curl -O http://example.com/file.txt
```

Change file or permissions
```
chmod 777 file
chmod -R 777 ./dir
```

Change to executable
```
chmod 0750 file
chmod +x file
```

Change file owner
```
chown -R owner ./dir
chown owner file
```

Change current user password and other user password
```
passwd
passwd USER
```

Find and kill a process
```
ps -A | grep <PROCESS>
kill -9 <PROCESS ID>
```

Check free hardrive space
```
df -h
```

Shutdown
```
sudo poweroff
```

Timestamps with [ISO 8601](http://www.w3.org/TR/NOTE-datetime)

With timezone
```
date +%Y-%m-%dT%H:%M:%S%:z
```
UTC
```
date -u +%Y-%m-%dT%H:%M:%SZ
```

For filenames
```
date -u +%Y-%m-%dT%H.%M.%SZ
```


Get folder size on OS X by file size, NOT disk usage
```
find . -type f -print0 | xargs -0 stat -f%z | awk '{b+=$1} END {print b}'
```

Get folder size on Linux by file size, NOT disk usage
```
find . -type f -print0 | xargs -0 stat -c%s | awk '{b+=$1} END {print b}'
```

Clear history and logout
```
rm ~/.bash_history; history -c; logout
```

Replace text using `sed`
```
sed -e 's/hello/hola/g;s/world/mundo/g;' < file.txt > out.txt
```

Replace ext. using `sed`
```
for i in *.md; do echo "$i" "$( sed -e 's/\.md$/.txt/g' <<< $i )"; done
for i in *.md; do echo "$i" "`sed -e 's/\.md$/.txt/g' <<< $i`"; done
```

Delete history and exit
```
cat /dev/null > ~/.bash_history && history -c && exit
```