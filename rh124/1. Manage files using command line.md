# List the contents of a directory.

```
ls
ls -l   # long listing
ls -a   # include hidden files
```

# Change directory.

```
cd /path/to/directory
cd ..    # move up one directory
cd ~     # move to the home directory
```

# Print the working directory.

```
pwd
```

# Create an empty file.

```
touch filename
```

# Copy files or directories.

```
cp source_file destination_file
cp -r source_directory destination_directory
```

# Move or rename files or directories.

```
mv old_filename new_filename
mv source_file /path/to/destination/
```

# Remove files or directories.

```
rm filename
rm -r directory_name   # remove directory and its contents
rm -i filename         # prompt before removal
```

# Concatenate and display the content of files.

```
cat filename
```

```
cat file1.txt file2.txt file3.txt > combined.txt
```
# Append the content of one file to another

```
cat file2.txt >> file1.txt
```

```
echo "Header" > combined.txt
cat file1.txt >> combined.txt
echo "Footer" >> combined.txt
```


# View file content one screen at a time.

```
more filename
less filename
```

# Display the first part of a file.

```
head filename
head -n 10 filename   # first 10 lines
```

# Display the last part of a file.

```
tail filename
tail -n 10 filename   # last 10 lines
```

#  Text editors for editing file content.

```
nano filename
vim filename
```

# Change file permissions.

```
chmod 644 filename   # set permissions to -rw-r--r--
chmod +x filename    # add execute permission
```

# Change file owner and group.

```
chown user:group filename
```

# Change group ownership.

```
chgrp group filename
```

# Archive files.

```
tar -cvf archive_name.tar directory_or_file
tar -xvf archive_name.tar   # extract
```

```
gzip filename
gunzip filename.gz
```

```
zip archive_name.zip filename
unzip archive_name.zip
```

# Search for files in a directory hierarchy.

```
find /path -name "filename"
find /path -type d -name "directory_name"  # find directories
```

```
locate filename
```

```
grep "pattern" filename
grep -r "pattern" /path   # recursive search
```

# Example1 : Practice Scenario.

```
# Create a directory structure
mkdir -p practice/{dir1,dir2,dir3}

# Create some files
touch practice/dir1/file1.txt
touch practice/dir1/file2.txt
touch practice/dir2/file3.txt

# Copy and move files
cp practice/dir1/file1.txt practice/dir2/
mv practice/dir1/file2.txt practice/dir3/

# View and edit files
nano practice/dir2/file1.txt
cat practice/dir3/file2.txt

# Change file permissions
chmod 755 practice/dir3/file2.txt

# Archive the directory
tar -cvf practice.tar practice/

# Search for files
find practice/ -name "file1.txt"
grep -r "text_pattern" practice/
```

# Example2 : Practice Scenario.

```
touch log1.txt
touch log2.txt
touch combined_logs.txt

echo "Log entry 1 from file1" > log1.txt
echo "Log entry 2 from file1" >> log1.txt
echo "Log entry 1 from file2" > log2.txt
echo "Log entry 2 from file2" >> log2.txt

cat log1.txt log2.txt > combined_logs.txt

cat combined_logs.txt
```
