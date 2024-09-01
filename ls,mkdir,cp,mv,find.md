```
ls # list all the file & dir in the current dir
ls /home # list all the files & dir from home dir
ls -l # long list, Directories are start with d, files start with -, it will disply in the following format permission, link, user, group, size, date, dir name or file name
ls -a # list hidden files also
touch .f4 # create hidden file

mkdir Dir1,dir2,dir3 # Create dir
mkdir -p A/B/C # create dir with sub dir
rm ab4 abc # delete files
rm a* # delete files are starting with a
rmdir AA1 # delete empty dir
rmdir -r AA2 # delete directory also if it is not empty


cp file1 file2 file3 A1 # copy files to A1 file, orginal file will not move
mv file1 file2 file3 A2 # move files to A1

find / -name passwd # find passwd from /
find . -name f1 # find f1 from current dir
find . -user root # find root user from current dir

mkdir /mnt/copy
sudo find / -name passwd -exec cp {} /mnt/copy /;
```


