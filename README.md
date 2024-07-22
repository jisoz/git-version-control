# git-version-control

git config --global user.name ""
git config --global user.email ""

git config --list


<!-- The git config --global user.name "" and git config --global user.email "" commands in Git are used to set your global username and email address, respectively. These values are important because Git uses them to record the author of commits. Here's why you need to configure these settings:

Identification: Every commit in Git has information about who made the changes. The user.name and user.email settings allow Git to properly attribute the work to you.
Global Configuration: Using the --global flag ensures that these settings apply to all repositories on your system. You can also set them on a per-repository basis without the --global flag if needed.
Consistency: Setting these configurations helps maintain consistent author information across all your repositories, making it easier to track contributions and manage code changes. -->

rename branch   git branch -m  old new  | delete branch  git branch -d ....
git branch 
git branch ....
git switch ....
git add  commit 
git push origin develop


working in other branch make file ...  git add git commit | switch to main git pull git merge other branch    git push

#revert or reset ???
<!-- if user already pushed commits to remote repo a revert is a nicer way to cancel out changes .
otherwise if changes just in local you can use reset  -->

reset:  git log 
        git reset --hard [previous log id] 

revert  when you finish push  and you want to revert last commit  git revert HEAD   git push


#stash git stash -a    git stash list git apply | git stash pop  (will remove from stash list)
