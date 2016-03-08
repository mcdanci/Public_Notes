# Notes for Pragmatic Version Control *Using Git*
> Author: McDanci

## First
To know the differences between centralized **V**ersion **C**ontrol **S**ystem and **D**istributed **V**sersion **C**ontrol **S**ystem.

## What Had Stored in the Repository?
* Working trees;
* Index (known as **staging area** too);
* Tags;
* Branches.

## Simple Settings
To set up your name and email address:

`git config --global user.name "{your name}"`
`git config --global user.email "{yours@email.info}"`

And have a check:

`git config --global --list`

## Usages
### Daily Usage
Seems everyone knows that:

* `git init`
* `git clone`
* `git pull`
* `git merge` (`git mergetool` is a related powerful command that you know)
* `git push`
* `git status`

Add files:
`git add .`

Advanced:
`git add -i`

Commit:
`git commit -m "{comment}"`

Modify the last commit:
`git commit --amend`

Have a view of the history log for a specified count:
`git log -{count}`

Want it one line per log?
`git log --pretty=oneline`

Or in graphical?
`git log --graph`

To start a graphical historical view in a new instance:
`gitk --all &`

To move sth.:
`git mv {sth.}`

New a branch by one of sth.:
`git branch {newB} {sth.}`

So as branch does, tag could be built by:
`git tag {newT} {sth.}`

Once `{oriB}` is the current branch, new a branch could be:
`git checkout -b {newB}`

And the deletion of branch:
`git branch -d {delB}`

Tags ditto:
`git tag -d {delT}`

Here you can also check out one of sth. (commits, branches and tags are included):
`git checkout {sth.}`

Rebase on sth.:
`git rebase {sth.}`

Once confiect occured during rebasing, you could use `git mergetool` too.

Help for anything:
`git help {sth.}`

### Powerful Commands
Arg with force:
`--force`

All those command args mentioned could be used in combinations.

Archive:
`git archive --format=zip --prefix={prefix} {arTag} {fileName}`

In the end, there is a concept that most of is based on VCS, named **C**onfiguration **M**anagement.
