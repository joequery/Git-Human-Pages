Git Add
=======

Human Summary
-------------
Inform git that file modifications since the last commit should be added to the
next commit. Creation of a file qualifies as a file modification, and in some
cases (-u and -A explained below), so does deletion of a file.

Technical Summary
-----------------
Updates the index in preparation for the next commit.

Usage
-----

If you want to start versioning a new file through git, use git add 

    touch somefile.txt
    git add somefile.txt
    git commit -m "Create somefile.txt"

If you make any modifications to somefile.txt, with the exception of deletion,
use git add again to add the modifications to the next commit.

    git add somefile.txt
    git commit -m "Modified somefile.txt"

Add all modifications to all files modified since the last commit to the next
commit. This includes newly created files, file modifications, and file
deletions.

    git add -A

Add all modifications to any file versioned through git that has been modified
by the last commit. The difference between this and -A above is that -A will
add newly created files to be committed, while this does not.

    git add -u

You can add multiple modifications to the next commit.

    git add f1.txt f2.txt

Wildcards can be used to conveniently add modifications of files with the same
extension to the next commit.

    git add *.py

If you're curious what modifications a git add command will add to the next
commit, you can set up a "dry run" with the -n flag.

    $ touch f1.txt
    $ touch f2.txt
    $ remove somefile.txt
    $ git add -n -A
    remove 'somefile.txt'
    add 'f1.txt'
    add 'f2.txt'
    

Function Details
-----------------

    git add [-n] [-v] [--force | -f] [--interactive | -i] [--patch | -p]
                     [--edit | -e] [--all | [--update | -u]] [--intent-to-add | -N]
                     [--refresh] [--ignore-errors] [--ignore-missing] [--]
                     [<filepattern>...]


