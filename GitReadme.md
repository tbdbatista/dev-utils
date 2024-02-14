# Git Commands

1. git add -p => opens a prompt for decision making before adding the changes listed in the current branch
2. git commit --amend => Update the last commit, this must be done before you push it to the remote branch.
3. git commit --amend --reset-author => update last local commit with the current configured user data
4. git commit --allow-empty -m "commit message" => create an empty commit if necessary
5. git reset --hard \<SHA> => Reset your branch to the typed hash.
6. git push --force (optional) => Reset everything on remote branch with the information of your local branch. ***Warning:*** don't use in shared branches as you will overwrite other user's progress.
7. git rebase -i \<SHA you want to squash to> => Squash commits into one.
8. git push origin +HEAD^:\<name of your branch> => discard last pushed commit on remote repository
9. git push origin \<SHA>:\<name of your branch> => discard all pushed commits on remote repository after \<SHA> reference

### Git Reset

01. git reset HEAD^ => remove last local commit and keep changes
02. git reset HEAD~2 => resets the HEAD pointer to two commits ago and keeps all changes in your working directory and staging area
03. git reset \<SHA> => remove all local commits after \<SHA> reference and keep all changes
04. git reset --soft HEAD => resets the HEAD pointer to the previous commit but keeps all changes in the staging area
05. git reset --hard HEAD => resets the HEAD pointer to the previous commit and discards all changes in the staging area and working directory

### Git Branches

01. git branch => lists all the local branches in the current repository.
02. git branch <branch_name> => creates a new branch with the specified name.
03. git branch -d <branch_name> => deletes the specified branch. Note that you cannot delete the currently checked-out branch.
04. git branch -D <branch_name> => forcefully deletes the specified branch, even if it has unmerged changes.
05. git branch -m <old_name> <new_name> => this command renames the specified branch.
06. git branch -a => lists all the local and remote branches in the current repository.
07. git branch -r => lists all the remote branches in the current repository.
08. git branch --merged => lists all the branches that have been merged into the current branch.
09. git branch --no-merged => lists all the branches that have not been merged into the current branch.
10. git branch --contains <commit> => this command lists all the branches that contain the specified commit.
11. git branch --list <pattern> => lists all the branches that match the specified pattern.

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

### When using -p flag

You'll be prompted with a few actions for each hunk:  

   y - stash this hunk  
   n - do not stash this hunk  
   q - quit; do not stash this hunk or any of the remaining ones  
   a - stash this hunk and all later hunks in the file  
   d - do not stash this hunk or any of the later hunks in the file  
   g - select a hunk to go to  
   / - search for a hunk matching the given regex  
   j - leave this hunk undecided, see next undecided hunk  
   J - leave this hunk undecided, see next hunk  
   k - leave this hunk undecided, see previous undecided hunk  
   K - leave this hunk undecided, see previous hunk  
   s - split the current hunk into smaller hunks  
   e - manually edit the current hunk  
   ? - print help  
