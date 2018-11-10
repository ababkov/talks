# Resources 

* Git Playground: https://learngitbranching.js.org/
* Gitflow: https://www.atlassian.com/git/tutorials/comparing-workflows/gitflow-workflow 

# The important bits you should understand

* Commits vs Tags vs HEAD vs Branches
    * Commit: Single piece of work 
    * Tag: Named commit (doesn't move)
    * HEAD: Always refers to current commit. When you commit to git, HEAD will move to new commit. .
    * Branch: Combination of Tag + HEAD. A reference to a commit that moves each time you commit over it. "Detached state" = checking out random commit not represented by a branch (hard to get back to).
* Cherry Pick vs Rebase (REWRITING HISTORY) vs Merge
    * Cherry picking - Copy one commit over... okay if desperate
    * Rebase - Like cherry picking but lots of commits. You are taking all of your commits in the branch since they diverged from another branch, ripping them out, rebranching from tip of thing you're basing stuff on and re-playing all of your commits over the top.
    * Merge - Create a new commit in your branch (most times) that includes all changes from whatever you're merging (since diverge).
* Why rebasing after a merge breaks... (new merge commit on your branch, master is still seperate, last common commit is still original commit where branch split off)
* Interactive Rebase
* What is a fast forward merge vs non fast forward merge

# Remote vs local branches

* origin/*
* git fetch vs git pull
* git (merge|rebase) origin/x OR git checkout origin/x is perfect valid (don't make changes on these branches though)
  
# Best practice

* Learn to not rely on a GUI! (You can still use one for conflict resolution, visualising branches etc but it should be exception not rule)
* Commit unrelated changes to different branches and / or develop
* Rebase often (but only if you're on a branch by yourself). Leaving it too long will make things hard (lots of conflicts).
* Don't try to rebase if you've already merged
* Don't rebase develop / master on your branch (ever)
* When merging from a branch into develop / master, make sure you do not fast forward
* `git stash apply` if unsure what's going to happen when you pop from your stash (easier to recover from).
* ? MORE ?

# Commands i use

* git diff 
* git diff HEAD^ (note HEAD can be any branch name, commit or tag) === git diff HEAD~1
* git diff HEAD^^ === git diff HEAD~2
* git diff HEAD~3
* git status
* git commit --amend (before you push)
* git add
* git checkout
* git checkout -b {branch}
* git reset
* git reset HEAD~#
* git reset --hard
* git reset HEAD^
* git rebase {branch name}
* git rebase --abort
* git rebase --continue
* git rebase master
* git merge --no-ff
* git pull --rebase
* git rebase -i
* git stash
* git stash pop
* git stash list
* git diff --staged
* git add -p (even though you guys will NEVER use this)
* git commit --allow-empty -m "An empty commit!"
* git log
* git reflog
* git checkout -B {branch}
* git update-index --assume-unchanged {something}
* git fetch
* `git branch -f master HEAD~3` vs `git checkout HEAD~3 && git checkout -B master`
* git branch -d {name}
* git branch -D {name}
* git prune
* git prune origin
* git push -f
* git cherry-pick {x} {y} {z}
* git revert (like reset but creates an undo commit)
