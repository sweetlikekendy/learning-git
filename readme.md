# Learning Git with Upcase

This repo is just a test repo for learning Git and Github.
https://thoughtbot.com/upcase/mastering-git

# Notes

## Merge

Fast-forward merge moves master to feature

`git merge --ff-only <feature>`

## Rebase

If feature branch has commits but is behind master, rebase feature to master. Feature branch commits will be orphaned, but still accessible.

`git rebase master`

### Interactive rebase

Interactive rebase is typically when feature branch is directly ahead of master. Take feature commits and squash down. It will use same tree ref as the unsquashed commits

`git rebase --interactive master`

## Stash

Stash untracked files

`git stash --include-untracked`
