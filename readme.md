# Learning Git with Upcase

This repo is just a test repo for learning Git and Github.
https://thoughtbot.com/upcase/mastering-git

# Notes

## Merge

Fast-forward merge moves master to feature

`git merge --ff-only <feature>`

## Push

Push commits from local branch upstream. Create pull request on Github. Add initials to your branch.

`git push -u origin storybook-styled-input:kn-storybook-styled-input`

## Rebase

If feature branch has commits but is behind master, rebase feature to master. Feature branch commits will be orphaned, but still accessible.

`git rebase master`

### Interactive rebase

Interactive rebase is typically when feature branch is directly ahead of master. Take feature commits and squash down. It will use same tree ref as the unsquashed commits

`git rebase --interactive master`

## Stash

Apply the last stash

`git stash apply`

Apply specific stash

`git stash apply stash@{0}`

Stash untracked files

`git stash --include-untracked`

Name stashes

`git stash save "WIP: making progress on foo"`

Start a new branch from stash

`git stash branch <new-branch> stash@{0}`
