GIT vs GITHUB
 Git is a free, open source version control tool that developers install locally on their personal computers, while GitHub is a pay-for-use online service built to run Git in the cloud

HEAD: 
The current commit your repo is on. Most of the time HEAD points to the latest commit in your current branch, but that doesn't have to be the case. HEAD really just means "what is my repo currently pointing at".

master: 
The name of the default branch that git creates for you when first creating a repo. In most cases, "master" means "the main branch". 

origin: 
The default name that git gives to your main remote repo. Your box has its own repo, and you most likely push out to some remote repo that you and all your coworkers push to. That remote repo is almost always called origin, but it doesn't have to be.

HEAD is an official notion in git. HEAD always has a well-defined meaning. master and origin are common names usually used in git, but they don't have to be.

GITHUB is the remote repository. Developers clone from the remote repository and working locally on a particular branch.

On Local dev machine- .git folder will keep track of two areas - local repository and staging area. It doesn't keep track of the changes done in working directory.

-----------------------------------------------------------------------------------------------------------------
[                 GIT on Developer Machine (git bash)              ]           ||    [GITHUB Remote Repository ]
-----------------------------------------------------------------------------------------------------------------
Working Directory   ||  Staging Area (index)   ||  Local Repository (HEAD)     ||      Remote Repository (Origin)
-----------------------------------------------------------------------------------------------------------------

~~~ working on GITHUB repository  in local environment
******************************************************
-> git clone => clones remote repository into local working directory

-> git switch "branch_name" => to point local repository to a partricular branch to work on (dev/bugfix/hotfix, etc) 
-> git switch -c "branch_name" => will create a branch if it doesn't exist in local repository

-> git add *.* => files modified/added/deleted in working directy's current branch are tracked by GIT for commit

-> git commit -m "change description" => commits changes to local reposity's current branch (new commit ID becomes HEAD)
-> git commit -a -m ... => authenticates (name and email) and commits changes to local repository's current branch

-> git push origin => pushes changes from Local repository to Remote repository
-> git push origin HEAD:dev => creates dev branch on remote repository and pushes local changes to remote dev branch

-> git pull - gets all changes of local repository's branch from remote repository and updates working directory

-> git fetch - gets info about all changes (not the changes) of all branches from remote repository to local repository only.
-> git merge - pulls actual changes from current branch and update working directory, resolving any conflicts.
:: git fetch allows user to switch to different branch using "git switch"

~~~ working on local repository that doesn't exist in GITHUB repositories
*************************************************************************
echo "# repository" >> README.md
git init
git add README.md
git commit -m "first commit"
git branch -M main
git remote add origin https://github.com/accountname/repositoryname.git
git push -u origin main

~~~ Informative GIT commands
****************************
-> git status => shows differences between working directory and local repository
-> git log --all --decorate --oneline --graph => displays commit history
-> git reflog => displays history of local commits
-> git init => will create .git folder to begin tracking changes in the working directory
-> git clean =>

-> git reset --hard/soft "commit id" => resets back to that particular commit. files and succesive commit logs will no longer be part of index.
-> git rebase
-> git revert



BASH window shortcuts
*********************
-> ctrl+L will clear BASH window
-> touch file.txt -> will create a file if it doesn't exist
->









