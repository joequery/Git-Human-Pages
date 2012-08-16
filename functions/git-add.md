git add
=======

Human Summary
-------------
Inform git that file modifications(*) should be added to the next commit.

(*) In the context of git, we specifically mean "file modifications since the
last commit"


Technical Summary
-----------------
Updates the index in preparation for the next commit.

Usage
-----

If you want to start versioning a new file through git, use git add 

    $ touch somefile.txt
    $ git add somefile.txt
    $ git commit -m "Create somefile.txt"

If you make any modifications to somefile.txt, with the exception of deletion,
use git add again to add the modifications to the next commit.

    $ git add somefile.txt
    $ git commit -m "Modified somefile.txt"

Add all file modifications to the next commit. This includes newly created
files, file modifications, and file deletions.

    $ git add -A

Add all modifications to any file already versioned through git. The difference
between this and -A above is that -A will add newly created files to be
committed, while this does not.

    $ git add -u

You can add multiple modifications to the next commit.

    $ git add f1.txt f2.txt

Wildcards can be used to conveniently add modifications of files with the same
extension to the next commit.

    $ git add *.py

If you're curious what modifications a `git add` command will add to the next
commit, you can set up a "dry run" with the -n flag.

    $ touch f1.txt
    $ touch f2.txt
    $ remove somefile.txt
    $ git add -n -A
    remove 'somefile.txt'
    add 'f1.txt'
    add 'f2.txt'
    

Further Uses
------------

# -v, --verbose

Be verbose. -n (dry-run) and -v output the same things, but -n prevents file
modifications from actually being added to the next commit.

    $ git add -v -A
    add 'functions/git-add.md'
    add 'testing.txt'

# -f, --force

Add a file that would normally be ignored (such as by .gitignore). Suppose you
currentlyare ignore all .log files, but you want to version a file called
error.log.

    $ git add -f error.log

# -p, --patch

Allows you to interactively add portions of modified files to the next commit.
Newly created and deleted files are ignored. This is useful if, for example,
you've added two functions in the same file since the last commit, but find the
creation of the two function merits two commits.

    $ git add -p mymodifiedfile.py    # Enter patch mode for single file
    $ git add -p                      # Enter patch mode for all modifications
    $ git add -p file1.txt file2.txt  
    
You will be greeted with a hunk of text, and options on what to do with it.

    Stage this hunk [y,n,q,a,d,/,j,J,g,e,?]?

Entering '?' will provide you with a menu that defines each option:

    Stage this hunk [y,n,q,a,d,/,j,J,g,e,?]? ?
    y - stage this hunk
    n - do not stage this hunk
    q - quit; do not stage this hunk nor any of the remaining ones
    a - stage this hunk and all later hunks in the file
    d - do not stage this hunk nor any of the later hunks in the file
    g - select a hunk to go to
    / - search for a hunk matching the given regex
    j - leave this hunk undecided, see next undecided hunk
    J - leave this hunk undecided, see next hunk
    k - leave this hunk undecided, see previous undecided hunk
    K - leave this hunk undecided, see previous hunk
    s - split the current hunk into smaller hunks
    e - manually edit the current hunk
    ? - print help


"Staging" is synonymous with "adding to the next commit" (or technically
speaking, adding to the index). '+' signs indicate additions that will be added
to the next commit if the hunk is staged, and '-' signs indicate deletions that
will be added to the next commit.

Man Page
--------

View the official man page
    
    $ man git-add
