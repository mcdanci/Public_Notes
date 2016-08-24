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
	* Straight merge: `git merge {mSth.}`
	* Squashed commits: `git merge --squash {mSth.}`
	* Cherry-picking: `git cherry-pick {mSth.}`
* `git push`
* `git status`

Add files:
`git add .`

Advanced:
`git add -i`

Commit:
`git commit -m "{comment}"`

without `-m {comment}`, editor would be called; you can also have a try of using `-v` at this time.

Modify the last commit:
`git commit -C HEAD --amend`

Have a view of the history log for a specified count:
`git log -{count}`

Want it one line per log?
`git log --pretty=oneline`

Or in graphical?
`git log --graph`

To start a graphical historical view in a new instance:
`gitk --all &`

To see what's the difference between the working tree and index (staging area):
`git diff`

Or to see what cached in staging area?
`git diff --cached`

Or between working tree and HEAD?
`git diff HEAD`

To move sth.:
`git mv {sth.}`

New a branch by one of sth.:
`git branch {newB} {sth.}`

So as branch does, tag could be built by:
`git tag {newT} {sth.}`

Once `{oriB}` is the current branch, new a branch could be:
`git checkout -b {newB}`

Rename a branch:
`git branch -m {formerName} {newName}`

And the deletion of branch:
`git branch -d {delB}`

Tags ditto:
`git tag -d {delT}`

Here you can also check out one of sth. (commits, branches and tags are included):
`git checkout {sth.}`

Revert?
`git revert -n {sth.}`

Rebase on sth.:
`git rebase -i {sth.}`

Once confiect occured during rebasing, you could use `git mergetool` too.

Add a remote repo:
`git remote add {rRepo-name} {rRepo-URL}`

Remove a remote repo:
`git remote rm {rRepo-name}`

Help for anything:
`git help {sth.}`

### Powerful Commands
Arg with force:
`--force`

All those command args mentioned could be used in combinations.

Reset to HEAD, including the working tree:
`git reset --hard`

Archive:
`git archive --format=zip --prefix={prefix} {arTag} {fileName}`

Command alias, such as commit:
`git cconfig --global alias.cm "commit"`

## Tips in the End
Use SHA-1 id. for at least four digits.

Selecting 3 log since 3 hours before using arg:
`since="3 hours" -3`

And similar usage for minute or some day.

Select a duration using:
`{begining}..{ending}`

`^` stands for the parent node.

`~2` stands for the parent node of parent node (so called grandparent node ;-).

Your directed boss would like to see this:
`git diff --stat {sth.}`

To see who does the changes:
`git blame {file}`

To ignore some files, using `.gitignore`.

Git branches like **D**irected **A**cyclic **G**raph.

There is a concept that most of is based on VCS, named **C**onfiguration **M**anagement.
