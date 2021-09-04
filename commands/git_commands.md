## Update profile:
```java
git config --global user.name "Your Name"
git config --global user.email "youremail@yourdomain.com"
```

## Update default editor:

```java
git config --global core.editor emacs
git config --global core.editor /usr/local/bin/emacs
```

## See staged for commit changes
```java
git diff --cached origin/master
```
➜ git pull
There is no tracking information for the current branch. Please specify which branch you want to merge with.
```java
git branch --set-upstream-to=origin/<branch_name> <branch_name>
```
git against head
```java
git push origin HEAD:chore/collaborators_view --force
```
## Apply .gitignore to project
```java
git rm -r --cached .
git add .
git commit -m ".gitignore is now working"
```
## Clean up remote branches
```java
git fetch --all --prune
```

## Revert back to certain commit
```java
git reset 56e05fced 

## Moves pointer back to previous HEAD
git reset --soft HEAD@{1}

git commit -m "Revert to 56e05fced"

## Updates working copy to reflect the new commit
git reset --hard
```

## Remove N last commits
```java
git reset --hard HEAD~N
```

## Remove specific commit
```java
git revert --strategy resolve <commit>
```

## Move repo A to B
```java
cd B
git checkout master
git remote add A **url-of-repoA**
git fetch A
git merge A/master --allow-unrelated-histories
git push origin HEAD
git remote rm A
```

## Undo Rebase
```java
git reflog // find where rebase: ends
git reset --hard HEAD@{N}
```

## Squash N Commits locally
```java
git reset --soft HEAD~N &&
git commit
```

## Reset to Rebase
```java
g checkout development
g log // copy latest SHA
g checkout foo
g reset -q --soft (latest SHA)
g stash
g checkout development
g checkout -b bar
g stash pop
g commit -m “added feature”
g push origin HEAD
```

## Rebase with theirs strategy
```java
g rebase development -X theirs
```
