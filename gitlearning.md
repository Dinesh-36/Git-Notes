GIT LEARNING:



Git → a tool (software) that runs on your computer to track changes

GitHub → an online platform that stores Git repositories and helps with sharing/collaboration



What does '**git init'** do?



It turns a normal folder into a Git repository



After running it:



Git starts tracking changes in that folder

A hidden .git folder is created (this is the brain of Git)



**'git add'** → putting pages into a “ready to save” tray/moves changes into the staging area (prepares what will be saved)



**'git commit'** → taking a snapshot of everything in that tray/creates a snapshot of the staged changes in the Git history (repository)



**'git status'** ->	current state (what’s changed now)



**'git log'** ->	past history (what was saved before)



Local repo → on your computer (Git)



Remote repo → on GitHub’s servers





Step 1: Create a GitHub repo

============================

Click New Repository

Give it a name (e.g. my-first-repo)

Keep it empty (don’t add README yet for now)

Create repo



Step 2: Connect local project to GitHub

=========================================

git remote add origin https://github.com/your-username/my-first-repo.git



remote → GitHub connection

add → create connection

origin → name of the remote (standard name)

URL → your GitHub repo



Step 3: Send code to GitHub (push)

==================================



'git push -u origin main'



It uploads your commits from local Git → GitHub



Important note (Windows/GitHub default issue)

\----------------------------------------------



Sometimes your branch is called master instead of main.



Check with:



git branch



If it shows master, then use:



'git push -u origin master'



**git clone**

**=========**



**'git clone https://github.com/user/repo.git'**



**Copies a complete GitHub project to your computer for the first time.**



**Not just files—also:**

**-------------------**

**Full history (all commits)**

**Branches**

**Remote connection (origin already set)**



**Important insight:**

**------------------**

**After cloning:**



**You DO NOT need git init**

**You DO NOT need to add remote manually**

**GitHub connection is already set**



**git pull**

**========**

**'git pull origin main'**



**Updates your local project with changes from GitHub.**



**Git checks GitHub**

**Downloads new commits**

**Merges them into your local branch**



**Golden Rule**

**===========**

**Always git pull before you start working**



**Why?**



**Someone else may have updated the code**

**Prevents conflicts**



**People do:**

**----------**



**edit code → commit → push → error**



**But correct flow is:**

**--------------------**



**pull → edit → add → commit → push**



**Branching**

**=========**

**branch is an independent line of development.**



**It lets you work on a feature without affecting the main code.**



Step 1: See branches

\---------------------

git branch



Step 2: Create a new branch

\--------------------------

git branch feature-login



Step 3: Switch to a branch

\---------------------------

git switch feature-login



Step 4: Create + switch in one step

\-----------------------------------



git switch -c feature-login



Correct workflow

\-----------------

Step 1: Create feature branch



git switch -c feature-login



Step 2: Work on it

add code

commit changes



Step 3: Go back to main

git switch main



Step 4: Merge feature into main

git merge feature-login



Merge Conflicts

===============

A merge conflict happens when Git cannot automatically merge changes from two branches.



Two branches changed the same part of the same file, and Git doesn’t know which version to keep.



So Git stops and asks:



“You decide.”



After resolving conflict, many people stop here:

\----------------------------------------------



git add .



and forget:



git commit -m "resolve merge conflict"



Until you commit:

\----------------



Git still considers the conflict unresolved

merge process is incomplete

you cannot safely continue work



When does it happen?

\--------------------



Usually when:



Two people edit the same file

Or you edit the same line in both main and a feature branch

Or you forgot to git pull before working(Why “forgot to git pull” causes conflicts



When you don’t run:



git pull



before starting work, this can happen:



🧠 Scenario

1\. Remote (GitHub) already changed



Someone else updates main:



Hello from teammate



2\. Your local copy is outdated



You still have:



Hello world



3\. You start editing based on old code



You change the same lines.



4\. Now you try to push/merge



Git sees:



Remote version changed

Your local version also changed

Same lines modified differently



Conflict happens)



















