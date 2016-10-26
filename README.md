#Git Command
##
###Set your identity for first time user. So it show your name and details when you commit.
```bash
git config --global user.name "Your Name"
git config --global user.email abcdefs@example.com
```

### To clone particular branch of git
```bash
git clone -b <branch_name> <remote_repo>(git@github.com:prashantkoshta/angularjs-dashboard.git)
```
### To checkout particular branch
```bash
git checkout <branch_name>
```
### To create new branch form existing branch. 
- Checkout branch from which you want to create new branch. Like i checkout master and from master i am createing new branch `dev_0.1`
```bash
git checkout <exiting_branch_name>
git checkout -b <new_branch_name>
git push <remote-name> <branch_name>
```
Where `<remote-name>` is typically `origin`, the name which git gives to the remote you cloned from.
Example:
```bash
git checkout master
git checkout -b dev_0.1
git push origin dev_0.1
```
### To commit changes on git
- check git status
```bash
git status
```
- add modifed files. `.` show add all modified files. If you need to add specific file give file name instead of `.`.
```bash
git add .
```
- Check file status
```bash
git status
```
- Commit changes
```bash
git commit -m "<YOUR_COMMENTS_ON_COMMIT>
```
- Push changes
```bash
git push
```
### To pull changes into local from remote branch.
```bash
git pull
```
### Set Beyond Compare as difftool for git.
```bash
git config --global diff.tool bc3
git config --global difftool.bc3.path "C:/Program Files (x86)/Beyond Compare 3/BCompare.exe"
```
### Show last log. -4 show last 4 logs.
```bash
git log -4
```
### To check file difference by BC tool.
```bash
git difftool
```
### To check difference between local version with remote version.
```bash
git fetch origin
git diff <branch_name> origin/<branch_name>
```
If difftool already set then
```bash
git fetch origin
git difftool <branch_name> origin/<branch_name>
```
### To clean untracked git file
```bash
git clean -df
```

### To reset local version with remote branch (revert local changes)
```bash
git reset --hard HEAD
```

### Show list of file changed form last commit. If you like to see previos 2 then use `HEAD~2`.
```bash
git diff --name-only HEAD HEAD~1
```
### Merging branch and solving conflicts
Assuming you have 2 branch master and dev_0.1. dev_0.1 is 2 commit behind the master. Now we have to merge master changes into dev_0.1. So my dev_0.1 will includ all master recent changes. 
```bash
git checkout <branch_name> Like dev_0.1
git merge <remote_name>/<branch_name> Like git merge orgin/master
```
- It may show confilit or auto merge changes.
- If it show confilit then your branch bash path show like `(dev_0.1|MERGING)`. In this case we have confilict on code. It dispaly like this in confilict files.
```bash
<<<<<<< HEAD
	res.send("Hello world now");
=======
	res.send("Hello World Master Change");
>>>>>>> origin/master
```
- Next step remove confilict from files and chek file status and commit then push.
```bash
git status
git commit -m "<YOUR_COMMENTS_ON_COMMIT>"
git push
```
###To see the current configured remote repository for your fork.
```bash
git remote -v
origin  https://github.com/YOUR_USERNAME/YOUR_FORK.git (fetch)
origin  https://github.com/YOUR_USERNAME/YOUR_FORK.git (push)
```
###To add upstream in your fork to push changes into main respositroy from your fork repository.
```bash
git remote add upstream https://github.com/octocat/Spoon-Knife.git
```
```bash
git remote -v
origin    https://github.com/YOUR_USERNAME/YOUR_FORK.git (fetch)
origin    https://github.com/YOUR_USERNAME/YOUR_FORK.git (push)
upstream  https://github.com/ORIGINAL_OWNER/ORIGINAL_REPOSITORY.git (fetch)
upstream  https://github.com/ORIGINAL_OWNER/ORIGINAL_REPOSITORY.git (push)
```
###To Delete git branch from local/remote
- Moveout from brach which you like to delete, checkout any other branch.
Example: I like to delete dev_0.1 branch. So i checkout master branch
```bash
git branch
git checkout <branch_name> 
git branch -d <delete_branch_name> //Use -D instead to force deletion without checking merged status
git branch
git push origin --delete <delete_branch_name> // This will push changes in remote branch.
```
Like:
```bash
git checkout master
git branch -d dev_0.1
git push origin --delete dev_0.1
```
###stash your local chagnes
-Use this if you like to save your local changes but dont want to commit until its not completed and do some work on other branch.
```bash
git stash list // show list of stash code.
git stash // Create stash
git stash pop //Pop your stash code
```
Example:
```bash
git checkout dev_0.1
.... Made some changes on code.
git stash
git checkout master
git checkout dev_0.1
git stash pop	
// Pop all local changes on which i kept save in stash but not commited and continue my work from there.
```

###Set env variable in window by git bash
```bash
export JAVA_HOME="/C/Program Files/Java/jdk1.7.0_79"
echo $JAVA_HOME
```
###Set environment variable in git base
- Go to git bash home directory. It is genrally `C:\Users\user_name`
```bash
touch .bashrc
```
- Edit `.bashrc` with required env variables
```bash
export JAVA_HOME="/C/Program Files/Java/jdk1.7.0_79"
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

### Revet changes in git branch
```bash
git log
git revert --no-commit 5fde377..HEAD // 5fde377 commit number
git commit -m "Revert changes"
git push
````



[![Analytics](https://ga-beacon.appspot.com/UA-70337513-4/chromeskel_a/readme?pixel)](https://github.com/prashantkoshta/developer-hand-book)
