# Git
open source distibuted version control system 
![image](https://github.com/user-attachments/assets/7b328859-6e0d-46fd-90e7-cfaacdd8e288)
 - git clone ....   (Copies a remote Git repository from a URL (e.g., GitHub, GitLab) onto your local machine)
Git automatically:

Creates a connection to the remote repository.

Names this connection origin.

So, origin is just a shortcut name for the URL of the remote repository.
   
- git add .  (Adds all changes in the current directory (and subdirectories) to the staging area , Staging area:
A place where Git collects changes before committing them. Think of it like preparing your changes before making them permanent.)

- git commit -m "test" (Takes the staged changes and records them in the repository as a commit with a message)
- git push origin main (Sends your local commits to the main branch of the origin remote repository)
- git pull origin main (Fetches the latest changes from the main branch on the origin remote and merges them into your current local branch)

# github 
![image](https://github.com/user-attachments/assets/c30e38e0-11d0-4c70-950e-06e696b8c56c)





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



# add existing project to a github repo 
1- create the empty repo 
2- in cmd in the project folder make sure that there is no .git folder  (Remove-Item -Recurse -Force .git)
3- git init 
4-  git commit -m "Initial commit"
5- git remote add origin https://github.com/jisoz/jad-portfolio.git ( the repo that you created in step 1 )
6- git push -U origin main  
7  if by mistake puted the master branch you can delete it and merge contenets to main : 
  git checkout main | git merge master --allow-unrelated-histories | (git branch -D master delete it locally ) 
  to dlete it remotly make sure you ar ein main and make git push origin --delete master
