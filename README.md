export GRADLE_HOME="/C/Users/gradle-2.10"
export ANDROID_HOME="/C/Users/android-sdk-windows"
export MAVEN_LOCAL_DIR=$ANDROID_HOME/extras/android/m2repository
export PATH=$PATH:$JAVA_HOME/bin:$GRADLE_HOME/bin:$ANDROID_HOME/tools:$ANDROID_HOME/platforms
```
###Working with fork and upstream
- Check upstream branch
```bash
git remote -v
```
- Add upstream branch into fork
```bash 
git remote add upstream https://github.com/test/test-demo.git
```

- Get upstream branh into fork, which is not present in fork.
```bash
git fetch upstream
git checkout <UPSTREAM_BRANCH_NAME>
git push origin <UPSTREAM_BRANCH_NAME> // It will add branch in fork repository
```

- Reset local changes in fork repository branch with upstream branch
```bash
git reset --hard upstream/<BRANCH_NAME>
```

- pull changes from upstream branch to fork repo branch
```bash
git pull upstram <branch_name>  // Fix confilicts if you get any.
git add .
git commit -m "<COMMENTS>"
git push origin <BRANCH_NAME>
```
- To merge upstream changes into fork branch / syncing a fork
```bash
git fetch upstream
git diff upstream/<BRANCH_NAME> origin/<BRANCH_NAME>
git merge upstream/<BRANCH_NAME>  // Fix confilicts if you get any.
git status
git add .
git status
git commit -m "<COMMENTS>"
git push origin <BRANCH_NAME>
```

- To abort rebase skip or continue
```bash
git rebase --continue
git rebase --skip
git rebase --abort // it move to dev_0.1 from (dev_0.1|REBASE 2/3) 
```


[![Analytics](https://ga-beacon.appspot.com/UA-70337513-4/chromeskel_a/readme?pixel)](https://github.com/prashantkoshta/developer-hand-book)
