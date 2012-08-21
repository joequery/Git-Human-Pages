git status
==========

Human Summary
-------------
View a list of files that have one of the following properties:

    * is currently untracked by git (and not ignored)
    * has been changed since the last commit
    * has been changed since the last commit AND is staged(*) to be commited
    * was previously staged but has since been modified

(*) See "Index/Staging Area" in the terms file. 

Usage
-----

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
