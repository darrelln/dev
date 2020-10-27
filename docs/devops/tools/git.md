---
layout: default
title: Git
parent: TOOLS
grand_parent: DEVOPS
has_children: false
has_toc: true
---

{% include toc.html %}

## References

[Git add and commit in one command](https://stackoverflow.com/questions/4298960/git-add-and-commit-in-one-command)

## Notes
Use ` on Linux and " of windows. For example:

```
// This won't work on Windows, but will on Linux.
git config --global alias.add-commit `!git add -A && git commit`

// This will work on Windows.
git config --global alias.add-commit "!git add -A && git commit"
```

## Command Reference

|Command|Details|Notes
|:---|:---|:---
|**Config file locations.**||
|~/.gitconfig|Global settings file.|
|.git/config|Per-project settings file.|
|**General configuration.**||
|`git config --global user.name <your name>`|Configure user name.|Before committing changes configure `user.name` and `user.email`
|`git config --global user.email <your email>`|Configure email.|
|`git config --global credential.helper {cache or 'cache --timeout=<seconds>'}`|Cache credentials for the likes of Visual Studio Code|
|**Getting help on a command.**||
|`git status -h`|Get help on the status command.|
|`git add -h`|Get help on the add command.|
|**Creatign a repo.**||
|`git init`||
|**Cloning repos.**||
|`git clone https://github.com/username/repo.git`|Clone a repo.|For private repos, use your two-factor key instead of password.
|**View status of local repo.**||
|`git status`|Show status of local repository.|
|**Stage changes.**||
|`git add {. or *}`|Add all modified files.|
|`git add /path/to/file`|Add specified file.|
|**Commit changes.**||
|`git commit -a -m "Commit message."`|Commit all changes.|Run `git add .` first.
|`git commit -m 'Commit message.'`|Commit staged changes.|
|**Push changes.**||
|`git push`|Push changes to remote repo.|
|**Pull changes.**||
|`git pull`|Pull the current branch.|
|**Branching and merging.**||
|`git branch`|Show active branch.|
|`git branch -a`|List all branchs (current branch shown in green).|
|`git branch button-feature`|Create a new branch named 'button-feature'.|
|`git checkout button-feature`|Change to a branch 'button-feature'.|
|`git checkout -b feature2`|Create new branch 'feature2' and checkout.|
|`git push --set-upstream origin button-feature`|Create the branch in the remote repo and switch.|
|`git branch -d feature1`|Delete fully-merged bramch 'feature1'.|
|`git branch -D feature1`|Force delete branch 'feature1' regardless of merge status.|
|`git merge feature2`|Merge branch 'feature2' into current branch.|
|**Create an alias.**||
|`git config --global alias.add-commit "!git add -A && git commit"`|Combine `git add` and `git commit` into a single command.|
|`git config --global --unset alias.add-commit`|Remove the `add-commit` alias.|

## Branching and merging.
Ideally create a new branch for every feature, make the changes, merge the changes back the main / master and delete the branch:
```
git branch                      // Check current branch.
git checkout -b new-feature     // Create a new branch from current branch and switch to it.
git add-commit -m "my changes." // Make and commit changes.
git push                        // Push changes.
git checkout main               // Ensure all you commit all your changes first.
git pull                        // Update the branch.
git merge new-feature           // Merge the new-feature branch into main.
git branch -d new-feature       // Delete the branch.
```