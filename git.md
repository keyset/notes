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
|`git config --global alias.pulld 'pull origin develop'`|alias `pulld` to `pull origin develop`|
|`git config --global alias.pushd 'push origin develop'`|alias `pushd` to `push origin develop`|
|`git config --global alias.deletemergedbranches '!git branch --merged \| egrep -v "(^\*\|master\|develop)" \| xargs git branch -d'`|`deletemergedbranches` finds all local branches already merged into trunk and deletes them|
|`git config --global alias.sudogc '!git remote prune origin && git gc'`|`sudogc` runs prune and garbage collect|
|`git config --global alias.rdone '!git pull origin develop --rebase && git rev-parse --abbrev-ref HEAD \| xargs -n 1 git push -f origin'`|`rdone` pulls latest updates in origin/develop, rebases current branch onto that, then force-pushes current branch to origin|
