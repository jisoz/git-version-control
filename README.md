# Git

![image](https://github.com/user-attachments/assets/7b328859-6e0d-46fd-90e7-cfaacdd8e288)

## Common Git Commands

### Cloning a Repository
- `git clone <repository-url>`  
  Copies a remote Git repository from a URL (e.g., GitHub, GitLab) onto your local machine.  
  **Git automatically:**
  - Creates a connection to the remote repository.
  - Names this connection `origin`.  
    > `origin` is just a shortcut name for the URL of the remote repository.

### Staging and Committing Changes
- `git add .`  
  Adds all changes in the current directory (and subdirectories) to the staging area.  
  **Staging Area:** A place where Git collects changes before committing them. Think of it like preparing your changes before making them permanent.

- `git commit -m "message"`  
  Takes the staged changes and records them in the repository as a commit with a message.

### Pushing and Pulling Changes
- `git push origin main`  
  Sends your local commits to the `main` branch of the `origin` remote repository.

- `git pull origin main`  
  Fetches the latest changes from the `main` branch on the `origin` remote and merges them into your current local branch.

---

# GitHub

![image](https://github.com/user-attachments/assets/c30e38e0-11d0-4c70-950e-06e696b8c56c)

---

![alt text](image.png)

---

![alt text](image-1.png)


#  Github Action Workshop

## software development lifecycle
requirements
design
code 
test 
deploy

## explore agile 
![alt text](image-2.png)

## devops lifecycle
![alt text](image-3.png)
![alt text](image-4.png)
![alt text](image-5.png)


## explaining merging methods 
1. rebase:
🧠 What it does:
Rewrites history by placing your feature branch commits on top of the target branch.

Avoids merge commits.

✅ Pros:
Cleaner, linear history.

Good for keeping commit logs tidy.

❌ Cons:
Changes commit hashes.

Can cause issues if rebasing shared branches.

📈 Visual:
Before:

css
Copy
Edit
A---B---C (main)
     \
      D---E (feature)
After:

mathematica
Copy
Edit
A---B---C---D'---E' (feature rebased)

usecase:Linear history without merge commits.

ex: remote master 
    local master 

in local master: git checkout -b cool_feature
                 git add . 
                 git commit -m 
                 git checkout master 
                 git pull 
                 git checkout cool_feature
                 git rebase master
                 git checout master
                 git rebase cool_feature
                 git push
                 
 

2. sqash merge
🧠 What it does:
Combines all changes from the feature branch into a single commit, then lets you commit it.

✅ Pros:
Very clean history — only one commit.

Great for merging large features into main.

❌ Cons:
You lose the individual commit history from the feature branch.

📈 Visual:
css
Copy
Edit
A---B---C (main)
     \
      D---E (feature)

↓ squash ↓

A---B---C---F (main, one commit for feature)

usecase : Clean commit history.

ex:
     git checkout bug_fix
     -- in this git log --oneline -> we see 3 commits but i dont want those 3 commits in main so 

     git checkout main 
     git merge feature --squash 
     git commit -m "one commit instead of 3" 


## github cli
isntall for windows
gh --version
gh auth login 
rh auth status

## versionning 

![alt text](image-6.png)


## Github actions workflow
stored in .github/workflows
written in YAML 
Automate Tasks


workflow triggers: 
![alt text](image-7.png)    
         

jobs:
![alt text](image-8.png)

tasks:
![alt text](image-9.png)

![alt text](image-10.png)


![alt text](image-11.png)

## github actions runner
a runner is a machine that executes job in a github actions workflows

- self hosted runner:
![alt text](image-12.png)

- github hosted runner:
![alt text](image-13.png)

![alt text](image-14.png)

## setup self-hosted runner:
in profile settings ->actions -> runner follow installation

## contexts

![alt text](image-15.png)

## variables and secrets : 

![alt text](image-16.png)


![alt text](image-17.png)

![alt text](image-18.png)

![alt text](image-19.png)

## expressions
![alt text](image-20.png)

![alt text](image-21.png)


## functions

![alt text](image-22.png)
![alt text](image-23.png)
![alt text](image-24.png)


##
![alt text](image-25.png)
![alt text](image-26.png)
![alt text](image-27.png)


## run jobs within containers
![alt text](image-28.png)

![alt text](image-29.png)

![alt text](image-30.png)

## actions

🧪 What is GitHub Actions?
GitHub Actions is a CI/CD (Continuous Integration/Continuous Deployment) tool built into GitHub.
It helps you automate workflows like:

Running tests

Building your code

Deploying to production

Sending notifications

Linting or formatting code

…and much more

⚙️ What is an "Action"?
In GitHub Actions, an "action" is a reusable, modular unit of code that performs a specific task in a workflow.

You can think of it as a function or script that's executed during the pipeline.

📦 3 Types of Actions
Type	Description	Example
Docker	Runs inside a container	Complex, isolated tasks
JavaScript	Written in Node.js, runs natively	Fast, common logic
Composite	Combines other actions/commands (YAML)	Simplified, reusable workflows

📄 Example Workflow (YAML)
yaml
Copy
Edit
name: CI Pipeline

on: [push]

jobs:
  build:
    runs-on: ubuntu-latest

    steps:
      - name: Checkout code
        uses: actions/checkout@v3   # ✅ This is an action

      - name: Set up Node.js
        uses: actions/setup-node@v3
        with:
          node-version: '18'

      - name: Install dependencies
        run: npm install

      - name: Run tests
        run: npm test
🔍 uses: vs run:
Keyword	Purpose	Example
uses:	Calls a predefined action	uses: actions/checkout@v3
run:	Runs a shell command	run: npm install

📚 Where Do Actions Come From?
Official GitHub actions: like actions/checkout, actions/setup-node

Community actions: from the GitHub Marketplace

Your own custom actions: from your repo or organization

✅ Benefits of Actions
Reusable: Write once, use everywhere

Modular: Break your CI/CD into clear steps

Scalable: Use thousands of public or private actions

Efficient: Reduces duplicated code in workflows
# Git Version Control

### Configuring Git
- `git config --global user.name "<your-name>"`  
- `git config --global user.email "<your-email>"`  
- `git config --list`  

> These commands set your global username and email address, which Git uses to record the author of commits.  
> **Why configure these settings?**
> - Identification: Properly attribute your work.
> - Global Configuration: Applies to all repositories on your system.
> - Consistency: Maintains consistent author information across repositories.

---

### Branch Management
- Rename a branch:  
  `git branch -m <old-name> <new-name>`

- Delete a branch:  
  `git branch -d <branch-name>`

- List branches:  
  `git branch`

- Switch branches:  
  `git switch <branch-name>`

- Push to a specific branch:  
  `git push origin <branch-name>`

### Working with Branches
1. Work in another branch and make changes:  
   `git add .` → `git commit -m "<message>"`  
2. Switch to `main`:  
   `git switch main`  
3. Pull the latest changes:  
   `git pull`  
4. Merge the other branch into `main`:  
   `git merge <branch-name>`  
5. Push the changes:  
   `git push origin main`

---

### Reverting or Resetting Changes
- **Reset (local changes only):**
  1. View commit history:  
     `git log`
  2. Reset to a previous commit:  
     `git reset --hard <commit-id>`

- **Revert (for pushed commits):**
  1. Revert the last commit:  
     `git revert HEAD`
  2. Push the changes:  
     `git push`

> **Note:** Use `revert` for changes already pushed to the remote repository. Use `reset` for local changes.

---

### Stashing Changes
- Save changes to stash:  
  `git stash -a`

- View stash list:  
  `git stash list`

- Apply changes from stash:  
  `git stash apply`

- Apply and remove from stash:  
  `git stash pop`

---

### Adding an Existing Project to a GitHub Repository
1. Create an empty repository on GitHub.
2. In the project folder, ensure there is no `.git` folder:  
   `Remove-Item -Recurse -Force .git` (Windows PowerShell)
3. Initialize Git:  
   `git init`
4. Commit the project:  
   `git commit -m "Initial commit"`
5. Add the remote repository:  
   `git remote add origin <repository-url>`
6. Push the changes:  
   `git push -u origin main`

### Deleting the `master` Branch (if needed)
1. Switch to `main`:  
   `git checkout main`
2. Merge `master` into `main`:  
   `git merge master --allow-unrelated-histories`
3. Delete `master` locally:  
   `git branch -D master`
4. Delete `master` remotely:  
   `git push origin --delete master`
