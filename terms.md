Git Terminology
===============

Refer to this document when you come across a term in the man pages you do not
know.

Branches
--------

A branch is a named collection of commits. The "master" branch is created when
the git repository itself is created. By convention, the master branch should
be your most production-ready branch. A very common scenario is to switch to a
new branch for a new feature, leaving your master branch unaffected by the new
feature addition until you explicitly merge the new feature branch with your
master branch. This is extremely useful since production bugs may be found
while developing a feature, and debugging the issue with an increased
complexity caused by the new, unfinished feature leads to an unpleasant
experience.

Commit
------

A commit is a collection of file additions, modifications, and deletions.  A
commit message describes the collection of file modifications for humans, such
as "Added README", or "Fixed memory allocation bug".
