# playground-git


## git merge
This command only merges a specified branch to your current one onto which you are standing.
```
git merge feature
```
This will merge feature branch to your master branch if you are on master branch and running this command.

## git rebase
This is generally used when we dont want to have a merging commits after we want to push our feature to master branch.
Suppose our master branch has 1 extra commit after where a branch feature is created.
Also feature branch has 2 commits.
Requirement: we want only one master branch which will have master's all commits + feature's 2 commits all in one line.
Steps:
1. Go to your feature branch
```
git rebase master
```
2. Go to your master branch
```
git rebase feature
```
Done.

## git pull
Git pull generally consist of git fetch and git merge. Run this command, it will fetch and pull for you.
```
git pull
```

## git fetch
The git fetch updates your so-called "remote-tracking branches" - typically these are ones that look like origin/master, github/experiment, etc. that you see with git branch -r. These are like a cache of the state of branches in the remote repository that are updated when you do git fetch (or a successful git push).

Suppose you have origin remote
```
git fetch origin
git diff master origin/master
```
Above will show you differences between your local master and your remote one which is on github.
If you like those changes do
```
git merge origin/master
```
This is better than directly doing git pull.

## Rules
1. Always go to your master and do "git pull" for it so that you should be always upto date with remote master. But I suggest use "git fetch" and then run "git diff master origin/master" to check out the differences in the files, change them so that there wont be any conflicts and then run "git merge origin/master"

2. Be aware when usinig rebase, as it deletes a branch.
