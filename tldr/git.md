#Git#

`git clone git@github.com:adam-rw/sysadmin-scripts.git` to  clone a repo from a remote server. A folder name can be added at the end of the command to override the repo name
`git add .` - Stages all changes for files not currently under version control. For safety use `git status` first to ensure it won't add any files you don't want committed
`git commit -am 'commit message' - Commits staged changes. Use `git status` to see what will be committed
`git push` - Pushes staged commit(s) to repo. You may need to use `git push origin master` if you're pushing to an empty repo for the first time
`git tag -a v1.2 9fceb02` - Adds a tag v1.2 to commit starting with 9fceb02 - useful for tagging releases 
`git revert 9fceb02` - Undoes a previous commit without losing history. Creates new commit with the changes
