# Git Commands

01. git commit --amend => Update the last commit, this must be done before you push it to the remote branch.
02. git reset --hard \<SHA> => Reset your branch to the typed hash.
03. git push --force (optional) => Reset everything on remote branch with the information of your local branch. ***Warning:*** don't use in shared branches as you will overwrite other user's progress.
04. git rebase -i \<SHA you want to squash to> => Squash commits into one.
05. git push origin +HEAD^:\<name of your branch> => discard last pushed commit on remote repository
06. git push origin \<SHA>:\<name of your branch> => discard all pushed commits on remote repository after \<SHA> reference
07. git reset HEAD^ => remove last local commit and keep changes
08. git reset \<SHA> => remove all local commits after \<SHA> reference and keep all changes

### Git Stash

01. git stash => stashes the uncommitted changes (staged and unstaged files)
02. git stash -u => stash untracked files
03. git stash -a => stash untracked files and ignored files
04. git stash -p => stash specific files
05. git stash list => list all stashes
06. git stash save <description> => add a description to the stash
07. git stash apply => reapply last stashed changes (that is, stash@{0})
08. git stash apply stash@{N} => reapply stash number N
09. git stash clear => empties the stash list by removing all the stashes
10. git stash drop <stash_id> => deletes a particular stash from the stash list
11. git stash branch <name of your branch> => applies stash to a new branch
