---
marp: true
theme: gaia
_class: lead
paginate: true
backgroundColor: #fff
---

# git 101

version control your code and collaborate on code

_presentation heavily borrowed from [infrastructureascode.ch](infrastructureascode.ch)_

----

# What is git?

git is a tool that was developped by Linus Torvald (of the Linux fame) because he was having trouble with legacy version control system they were using for Linux. git enables a number a functions out of the box:

- Version control
- 

----

# git vs github

Quick note: git is not github. git is a client/server application that enables the functions described in the last slide. Github is a git server platform. 

Github also enables a lot of different features that are not inherently part of git. This presentation will be using Github as the git server but primarily will explain how to use the git client.

----

# Glossary

- Repository: Where you put stuff. A folder on your workstation
    - Remote:
    - Origin:
    - Master:
- Branch:
- Clone:
- Commit:
- Checkout: 

----

# How Does it Work?

- You always work locally
- You don't have to have a remote repo
- You merge code later when you are happy with it.
- git tracks -everything- don't try to hide your mistakes. (me? mistakes? what are you talking about?)
- Branches are your friend, git is your friend.

-----

# Typical Workflow

![Alt text](https://www.nobledesktop.com/image/gitresources/git-branches-merge.png "git branches")

-----

# Let's get started!

Create a folder

    # mkdir test1 && cd test1 && ls -al

Output:

    total 8
    drwxr-xr-x 2 urs urs 4096 Jul 16 05:16 .
    drwxr-xr-x 4 urs urs 4096 Jul 16 05:16 ..

----

Let's have a look:

    # git status

Output: 

    fatal: not a git repository (or any of the parent directories): .git

The command git status is definitely worth to remember. 

The error message tells us that Git cannot find the .git directory. To create a Git repository in our local machine, we can initiate a new one or clone one from a remote server. Let's see first how we can create a new one.

----

    # git init

    Initialized empty Git repository in /home/urs/git101/test1/.git/


    # ls -al .git

    total 40
    drwxr-xr-x 7 urs urs 4096 Jul 16 05:18 .
    drwxr-xr-x 3 urs urs 4096 Jul 16 05:18 ..
    -rw-r--r-- 1 urs urs   23 Jul 16 05:18 HEAD
    drwxr-xr-x 2 urs urs 4096 Jul 16 05:18 branches
    -rw-r--r-- 1 urs urs   92 Jul 16 05:18 config
    -rw-r--r-- 1 urs urs   73 Jul 16 05:18 description
    drwxr-xr-x 2 urs urs 4096 Jul 16 05:18 hooks
    drwxr-xr-x 2 urs urs 4096 Jul 16 05:18 info
    drwxr-xr-x 4 urs urs 4096 Jul 16 05:18 objects
    drwxr-xr-x 4 urs urs 4096 Jul 16 05:18 refs

----

    # git status
    
    On branch master

    No commits yet

    nothing to commit (create/copy files and use "git add" to track)

Git created succesfully a new repository and now we can see the directory .git. We should never need to make any changes on this directory by hand. When we check the Git Status, we see that we have a clear repository. 

----

    # cat > README.md <<EOF

    # Test Project 1

    It is always good to have a README file as a entry point of reading in a project.
    The file doesn't have to be huge and perfect. As the project develops this file should too.

    ## ToDo

    - create some content
    - seize world domination
    - save the planet
    EOF

----

    # cat README.md

    # Test Project 1

    It is always good to have a README file as a entry point of reading in a project.
    The file doesn't have to be huge and perfect. As the project develops this file should too.

    ## ToDo

    - create some content
    - seize world domination
    - save the planet

----

    # git status

    On branch master

    No commits yet

    Untracked files:
    (use "git add <file>..." to include in what will be committed)

        README.md

Nothing added to commit but untracked files present (use "git add" to track)

After creating a new file with some content, we can see Git indicate that we have an untracked file.

----

    # git add README.md

    # git status

    On branch master

    No commits yet

    Changes to be committed:
    (use "git rm --cached <file>..." to unstage)

        new file:   README.md

Now we are ready for the first commit. But what is a commit? A commit is a snapshot of the changed files. 

----

# Your IDE Probably Can Help You



