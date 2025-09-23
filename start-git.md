# Git Cheatsheet

## Git Repository
- After you've created your folder, go into the folder
- `git init` : initialize your git repository
- `git log` : shows all the commits you have done

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

