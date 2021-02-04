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

### View Git config
> cat .git/config: 

### Create alias for git command
`git config --global alias.pushd "push -u origin HEAD"`

### Configure git to prune branches while fetching
`git config --global fetch.prune true`
