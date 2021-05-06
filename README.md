## Git cheat sheet

### Git commands
* git clone repo-url: Clone a repository
* git branch -a: Shows all the branches
* git branch -d branch-name: Deletes the local branch
* git branch -u origin/master: Set the remote tracking branch
* git branch -vv: Shows tracking changes
* git push -d origin branch-name: Deletes the remote branch
* git push -u origin HEAD: Push to remote branch having same name as the local branch
* git remote show origin: Shows all tracking info
* git remote set-head origin some_branch: Changes the HEAD
* git stash list [<options>]
* git stash show [<options>] [<stash>]
* git stash drop [-q|--quiet] [<stash>]
* git stash ( pop | apply ) [--index] [-q|--quiet] [<stash>]
* git stash clear
* git stash create [<message>]

### View Git config
> cat .git/config: 

### Create alias for git command
`git config --global alias.pushd "push -u origin HEAD"`

### Configure git to prune branches while fetching
`git config --global fetch.prune true`

### Reverting to previous commits
#### Way 1
* do the needed changes in the feature branch
> `$ git commit -m "fixed issues in feature-branch'`

* create new branch tracking dev branch (branch to which you merge)
> `$ git checkout -b revert-the-revert-branch -t dev`

* revert the reversion commit
> `$ git revert <revert-commit-hash> | git revert old_hash..new_hash`

* checkout the original feature branch
> `$ git checkout feature-branch`

* merge the revert branch (revert-the-revert-branch)
> `$ git merge revert-the-revert-branch`

* handle merge conflicts and commit and PR

#### Way 2
Reverting public commits
* Checkout the commit to revert to
> `git checkout -f [HASH] -- .`

* Create a new branch, the commit becomes the head of the branch
> `git checkout -b [New branch with reverted changes]`

* Commit the changes
> `git commit -a -m "Reverted the changes"`

* Push and create the PR
> `git push -u origin [New branch with reverted changes]`
