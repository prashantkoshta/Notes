##Linux Command

###To See environemnt variable
```bash
printenv
echo $path
```
###Set envirnment variable
```bash
export JAVA_HOME=/c/java
export path=$path:$JAVA_HOME/bin
```
###Find file 
```bash
find ./<DIR_NAME> -name '*.ext'
```
###Present working directory
```bash
pwd
```
###Change directory
```bash
cd ./home
cd ~ \\ to root directoy
```
###ls command - List directory contents
```bash
ls
ls -lrash
```
Some useful options are -l, -a, -s, -h and -R
where
-l will give you a long listing (as explained above)
-a will show you ALL the files in the directory, including hidden files
-R will the subdirectories recursively, which means it will show all the directories and files within the specified directory.
-s will also show you the size of the files (in blocks, not bytes)
-h will show the size in "human readable format" (ie: 4K, 16M, 1G etc). Of course you must use this option in conjunction with the -s option.

###Help Manual
```bash
man mv
```
###Remove Directoy and file
```bash
rm -rf ./temp
```
###grep command
The grep command is used to search text or searches the given file for lines containing a match to the given strings or words.
```bash
grep 'word' file1 file2 file3
grpe -r 'Hello World' ./dir_name  //  read all files under each directory for search 'Hello World'
```

###Common
```bash
celar // Clear terminal
echo "Test1" //echo message on scrren
mkdir //Create new folder(s)
ps //process status
rmdir //remove directory
rm //remove files
whoami // Print the current user id and name (`id -un')
who //Print all usernames currently logged in
man //help manual
mv ./soruce ./target Move or rename files or directories
mount //Mount a file system
kill  // to kill process by PID

```

###vi Editor
```bash
vi file.txt  //Open file in vi editor
```
Help on vi editor
- i insert text before cursor, until <Esc> hit
- I insert text at beginning of current line, until <Esc> hit
- ^f for forward screen
- ^b for backward screen
- Esc+ :wq for save and quit
- Esc+ :q! for quit without save.


### Create or Extract tar file
-Create
```bash
tar -cvf tarfilename.tar /path/to/directory  // Crate tar of give driectory
tar -cvf tarfilename.tar /path/to/file-1 /path/to/file-2 //To create an archive of certfain files
tar -cvf tarfilename.tar /path/to/directory --exclude="*.png" //To exclude certian file from tar.
```
-Extract
```bash
tar -xvf tar_file.tar
tar -xvf tar_file.tar note.txt //Extract single file from tar
tar -xvf tar_file.tar bin // Extract a single directory called bin,
```
-To see file and directory in tar without extract
```bash
tar -tf tar_filename.tar
```

###chmod command - To change permission
-chmod u=rwx,g=rx,o=r myfile 
Where, The letters u, g, and o stand for "user", "group", and "other" and the letters "r", "w", and "x" stand for "read", "write", and "execute". Each digit is a combination of the numbers 4, 2, 1, and 0.
4 stands for "read",
2 stands for "write",
1 stands for "execute", and
0 stands for "no permission."
So 750 mean U- (4+2+1)rwx, G- (0+4+1)rx, O-(0+0+0) NO permission
```bash
chmod 755 ./temp 
```


