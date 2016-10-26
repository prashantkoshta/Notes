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
