# Learning Git with Upcase

This repo is just a test repo for learning Git and Github.
https://thoughtbot.com/upcase/mastering-git

# Notes

## Merge

Fast-forward merge moves master to feature

`git merge --ff-only <feature>`

If commits are ahead of master and you need to pull a commits from master

https://thoughtbot.com/upcase/videos/git-thoughtbot-git-flow 17:39

`!git checkout master && git pull && git checkout -`

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

# Example Work Flow

1. Checkout a feature branch. You can specify the starting point.

   `git checkout -b <feature_branch> <starting_point_branch>`

2. Once you've finished, stage and commit your changes in your local branch.

3. When you're ready to push to Github, add your initials in front of your feature branch. This will tell other devs who worked on the branch just by looking at the name of the branch.

   `git push -u origin storybook-styled-input:kn-storybook-styled-input`

4. Check to see if your local branch is up-to-date with master before pushing.

   `git checkout main && git pull && git checkout -`

5. You can create a git alias for this by running `git config --global alias.mup '!git checkout main && git pull && git checkout -'` in your terminal.

   This will show up in the `~/.gitconfig` file as

   `mup = !git checkout main && git pull && git checkout -`

   To check your git aliases, add another alias

   `git config --global alias.alias '!git config --get-regexp ^alias\\. | sed -e s/^alias\\.// -e s/\\ /\\ =\\ /'`.

   To test this, you can run `git alias` and it should return

   `mup = !git checkout main && git pull && git checkout - `

   `alias = ! git config --get-regexp ^alias\\. | sed -e s/^alias\\.// -e s/\\ /\\ =\\ /`

6. To merge your branch with master, checkout to master, then run fast-forward merge.

   `git checkout <master_branch>`

   `git merge -`

   Note: Using '-' means just use the previous branch.

7. After merging, push your changes (you should be in master branch).

   `git push`

8. Finally, delete your feature branch.

   `git branch -d <feature_branch>`
