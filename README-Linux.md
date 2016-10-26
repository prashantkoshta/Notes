##Linux Command

###To See environemnt variable
```bash
printenv
echo $path
```
###Set envirnment variable
```bash
export JAVA_HOME=\c\java\
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
cd \home
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
mv Move or rename files or directories
mount //Mount a file system
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
- Esc+ :q for quit without save.
