git status
==========

Human Summary
-------------
View a list of files that have one of the following properties:

    * is currently untracked by git (and not ignored)
    * has been changed since the last commit
    * has been changed since the last commit AND is staged(*) to be commited
    * was previously staged but has since been modified

```git status``` is *extremely* useful to see what you're about to commit.

(*) See "Index/Staging Area" in the terms file. 

Usage
-----

Suppose ```myfile.txt``` and ```README.md``` are currently versioned under git.
If ```myfile.txt``` is modified,  ```git-status``` will show the following:

    # Changes not staged for commit:
    #   (use "git add/rm <file>..." to update what will be committed)
    #   (use "git checkout -- <file>..." to discard changes in working directory)
    #
    #       modified:   myfile.txt
    # 

All files listed under "Changes not staged for commit" will not have their
modifications added to the next commit. We must use ```git add``` to add the
file modifications to the next commit. If we were to run

    $ git add myfile.txt
    $ git status

We would see the following:

    # On branch master
    # Changes to be committed:
    #   (use "git reset HEAD <file>..." to unstage)
    #
    #       modified:   myfile.txt
    #

All files listed under "Changes to be committed" **will** have their
modifications added to the next commit.

Further Uses
------------

Technical Summary
-----------------
Displays paths that have differences between the index file and the current
HEAD commit, paths that have differences between the working tree and the index
file, and paths in the working tree that are not tracked by git (and are not
ignored by gitignore)

Man Page
--------

View the official man page
    
    $ man git-status
