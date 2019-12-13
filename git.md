|`Command`|Notes|
|---|---|
|`git branch -a`|list all branches including local copies of origin|
|`git branch --merged \| egrep -v "(^\*\|master\|dev)"`|list merged branches|
|`git branch --merged \| egrep -v "(^\*\|master\|dev)" \| xargs git branch -d`|delete merged branches|
|`git remote prune origin`|remove local origin branches that have been deleted from remote|
|`git gc`|garbage collect|
|`git clean -xdf`|remove all untracked, uncommitted, and ignored files|
|`git rebase develop`|rewind current branch to where it diverged from `develop`, fast-forward to tip of `develop`, replay current branch's commits|
|`git stash list`|show the stash stack|
|`git config --global alias.pullc '!git rev-parse --abbrev-ref HEAD \| xargs -n 1 git pull origin'`|alias `pullc` to `pull origin currentBranch`|
|`git config --global alias.pushc '!git rev-parse --abbrev-ref HEAD \| xargs -n 1 git push origin'`|alias `pushc` to `push origin currentBranch`|
