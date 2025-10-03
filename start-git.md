# Git Cheatsheet

## Git Repository
- After you've created your folder, go into the folder
- `git init` : initialize your git repository
- `git log` : shows all the commits you have done
  - `git log --oneline` : shows one line logs
  - `git log --stat` : shows insertions and deletions for each commit
  - `git log -p` : shows more detailed information for each commit
  - `git log --pretty=format:"%h - %an, %ar : %s"`
    - `%h` : abbreviated commit hash
    - `%an` : author name
    - `%ar` : author date, relative
    - `%s` : subject (commit message)
  - `git log --since=1.week` : commit from the last week
  - `git log --after="2023-06-01" --before="2023-06-30"` : specifc dates ( also can use --until, --before, --after, --since)
  - `git log --grep="function"` : can use grep to search for specific words in the commit message
  - `git log -- script.js` : can search using the file name
  - `git log -S "console.log"` : changes where console.log changes
  - `git log -p --since=1.week -- script.js` : detailed changs to a file in a specific timeframe
- `git shortlog -s -n` : see a summary of commits by author
- `git rev-list --count HEAD` : see total number of commits
 
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

## Tags
  - `git show <tag-name>` : shows the tag
  - `git tag -l "v1.*"` : another way to list tags
  - `git tag -n` : list tags with their first line of message
  - `git checkout <tag0name>` : enter your commit and can make changes
    - if you make changes you can retain them by creating a new branch `git checkout -b branch-name <tag-name>`
  - `git tag -d <tag-name>` : delete a tag
  ### Lightweight Tags
  - `git tag v0.1` : creates a tag names v0.1 pointing to the current commit (HEAD). this is a lightweight tag
  - `git tag v0.0.1 <commit-hash>` : creates a tag for a past commit ( just go to git log --oneline to get the hash)
  - `git tag` : shows your list of tags
  ### Annotated Tags (includes taggers name email date and tagging message)
  - `git tag -a v1.0 -m "First major release"` : the -a specifies an annoted tag
    

    
