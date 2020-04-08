# GIT

## Finish work on a branch and merge back to master

* You are currently on the feature branch
* Update master branch
```
    git status
    git branch
    git checkout master
    git pull
```

* Merge master into feature branch (necessary when people working in parallel on different branches)
```
    git checkout <features/branch_name>
    git merge master
    git push
```

* Merge feature branch into master
```
    git checkout master
    git merge --no-ff <features/branch_name>
    git push
```

* Delete feature branch (local and remote)
```
    git branch [-a]
    git branch -d <features/branchname>
    git push origin :<features/branch_name>
    git branch [-a]
```

## Git commit ID of last commit
```
    git log -n1
```

## Correct log message AFTER commit but BEFORE push
```
    git commit --amend
```

## Merge fixes branch into master (all changes from fixes branch into master)
```
    git merge -s ours <features/branch_name>
```

## React on rejected `git push`
```
    git status
    git pull --rebase
    git push
    git status
```

## Create a new feature branch
```
    git checkout -b <features/branch_name>
    git push origin <features/branch_name>
    git branch --set-upstream <features/branch_name> <origin/features/branch_name>
```

## Reset history and continue from earlier commit
```
    git reset --hard <commit-id>
    git push -f origin master
```

## Show git branches and creator
```
    git for-each-ref --format='%(committerdate) %09 %(authorname) %09 %(refname)' | sort -k5n -k2M -k3n -k4n
```

## Find all deleted file
```
    git log --diff-filter=D --summary | grep delete
```

## Find all commits of a certain file
```
    git log --all -- FILE_PATH_FOUND --> COMMIT_ID
```

## Find content of a certain file
```
    git show COMMIT_ID -- FILE_PATH_FOUND
```
