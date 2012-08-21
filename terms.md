Git Terminology
===============

Refer to this document when you come across a term in the man pages you do not
know.

Branches
--------

A named collection of commits. 

Commit
------

A saved collection of file additions, modifications, and deletions.  A commit
message describes the collection of file modifications for humans, such as
"Added README", or "Fixed memory allocation bug".

Index/Staging Area
------------------

A collection of file additions, modifications, and deletions that will be saved
upon the next commit. 

HEAD
----

It's generally safe to think of HEAD as the currently checked-out branch. In
many cases, HEAD resolves to the last commit of the current branch. (See ```git
revert``` and ```git reset``` for examples)
