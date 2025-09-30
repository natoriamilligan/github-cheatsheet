# Git Cheatsheet

## Git Repository
- After you've created your folder, go into the folder
- `git init` : initialize your git repository
- `git log` : shows all the commits you have done
  - `git log --oneline` : shows one line

## Configurations
- `git-config-lab` folder : folder that holds all your configurations
- `git config --list ` : lists all configurations
- `git config --global user.name "Natoria Milligan" (sets user.name globally to Natoria Milligan)
  -There are 3 types of configuration levels
    - System level
    - Global Level
    - Local level
- `git config --global color ui auto` : sets colors to auto when terminal outputs (to verify the setting use "git config --global color.ui")
- `git config --global core.editor nano` : setting your log editor to nano"
- `git config --global alias.st status` : creates a shortcut called st for status
- **You can remove the `--global` to create a temporary (experimental configuration)**

## Files
- `.gitignore` : file that tracks files that you don't want commited
- `git diff` : shows what changes you have made before you commit
- `git diff --staged` : shows changes you've staged but haven't commited yet
- `git restore --staged hello.py` : unstage a file

## Branch Operations
- `git branch branch-name` : create a new branch
- `git branch`: shows all branch and an `*` to show which brnach you are in
- `git checkout (or switch) branch-name" : switches to another branch and updates files in branch you were in
  - `git switch -c feature-dimension` : create and move to the new branch in one command
- `git merge new-branch` : merge files from one branch to another
- git branch --merged` : see all branches that have been merged into current branch
- `git branch -d other-branch` : delete a branch if the branch has been merged (use -D if you want to delete if it hasnt been merged)
- `git commit --amend -m "Adding to previous commit and revising message"` : adds the commit to the previous commit and overwrites previous message. (omitting the -m will open the text editor so you can modify the previous message)
- `git revert HEAD` : reverts previous commit
- `git cherry-pick second-branch` : merges last commit to branch you are in from another branch
  ### Rebasing
    - `git rebase -i HEAD~3` : go back 3 commits
    - `git commit --amend -m "changed commit` : this is how you change a commit when rebasing outside of the text editor
 
## Stashing
**Make sure to keep a running tab of your stashes**
- `git stash' : stash away commits. Only stashes tracked files and stages changes (use -u to include untracked files)
- `git stash push -u -m "Make commit"` : stashes and adds comments
- `git stash list` : to see a list of the stashed files
- `git stash apply` : applys the most recent stash to your directory but keeping the stash in the stash list
  - `git stash apply stash@{1}` : re applies other stashes
- `git stash clear` : deletes all stashes
- `git stash pop` : applies changes from your most recent stash to your working directory and then removes that stash from the list
- `git stash branch feature-branch` : after stashing, you can use this command to move that stash to another branch. Then the stash is removed from the stashed list
- `git stash branch feature-branch` : removes a specific stash
