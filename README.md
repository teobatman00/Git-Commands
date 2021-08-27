Git Commands
============

## Translated Versions
- [Versão em português](READMEpt.md)

___

_A list of my commonly used Git commands_

*If you are interested in my Git aliases, have a look at my `.bash_profile`, found here: https://github.com/joshnh/bash_profile/blob/master/.bash_profile*

--

### Getting & Creating Projects

| Command | Description |
| ------- | ----------- |
| `git init` | Initialize a local Git repository |
| `git clone ssh://git@github.com/[username]/[repository-name].git` | Create a local copy of a remote repository |

### Basic Snapshotting

| Command | Description |
| ------- | ----------- |
| `git status` | Check status |
| `git add [file-name.txt]` | Add a file to the staging area |
| `git add path/to/[file-name.txt]` | Add a directory file change to the staging area |
| `git add path/to/directory` | Add all changes in the directory to the staging area |
| `git add .` | Add all the changes to the staging area|
| `git add -A` | Add all new and changed files to the staging area |
| `git commit -m "[commit message]"` | Commit changes |
| `git commit -m "[commit message]" -m "[commit message description]"` | Commit changes with description |
| `git rm -r [file-name.txt]` | Remove a file (or folder) |

### Branching & Merging

| Command | Description |
| ------- | ----------- |
| `git branch` | List branches (the asterisk denotes the current branch) |
| `git branch -a` | List all branches (local and remote) |
| `git branch [branch name]` | Create a new branch |
| `git branch -d [branch name]` | Delete a branch |
| `git push origin --delete [branch name]` | Delete a remote branch |
| `git checkout -b [branch name]` | Create a new branch and switch to it |
| `git checkout -b [branch name] origin/[branch name]` | Clone a remote branch and switch to it |
| `git branch -m [old branch name] [new branch name]` | Rename a local branch |
| `git checkout [branch name]` | Switch to a branch |
| `git checkout -` | Switch to the branch last checked out |
| `git checkout -- [file-name.txt]` | Discard changes to a file |
| `git merge [branch name]` | Merge a branch into the active branch |
| `git merge [source branch] [target branch]` | Merge a branch into a target branch |
| `git stash` | Stash changes in a dirty working directory |
| `git stash clear` | Remove all stashed entries |

### Sharing & Updating Projects

| Command | Description |
| ------- | ----------- |
| `git push origin [branch name]` | Push a branch to your remote repository |
| `git push -u origin [branch name]` | Push changes to remote repository (and remember the branch) |
| `git push` | Push changes to remote repository (remembered branch) |
| `git push origin --delete [branch name]` | Delete a remote branch |
| `git pull` | Update local repository to the newest commit |
| `git pull origin [branch name]` | Pull changes from remote repository |
| `git remote add origin ssh://git@github.com/[username]/[repository-name].git` | Add a remote repository |
| `git remote set-url origin ssh://git@github.com/[username]/[repository-name].git` | Set a repository's origin branch to SSH |
| `git remote add [remote name] [url]`| Add remote repository server address|
| `git remote [-v / --verbose]`| Display all remote repository |
| `git fetch --all` | Fetch all remote repository |
| `git fetch [remote name]` | Fetch a remote source repository |

### Inspection & Comparison

| Command | Description |
| ------- | ----------- |
| `git log` | View changes |
| `git log --summary` | View changes (detailed) |
| `git log --oneline` | View changes (briefly) |
| `git log --oneline --graph` | View changes (briefly) (graphical representation) |
| `git diff [source branch] [target branch]` | Preview changes before merging |

### Rebase 

         A---B---C topic
        /
    D---E---F---G master

***Would be***

                  A'--B'--C' topic
                 /
    D---E---F---G master

| Command | Description |
| --------| ----------- |
| `git rebase [target branch]` | Set [target branch] to be base branch for this branch |
| `git rebase [target branch] [source branch]` | Set [target branch] to be base branch for [source branch] |
| `git rebase --onto [first branch] [second branch] [...] [last branch]` | Set rebase for multiple branch |

***Example***
`git rebase --onto master topicA topic`

    o---o---o---o---o  master
            |            \
            |             o'--o'--o'  topic
             \
              o---o---o---o---o  next

***Will be***

                           H---I---J topicB
                           /
                  E---F---G  topicA
                 /
    A---B---C---D  master

### Submodules

| Command | Description |
| --------| ----------- |
| `git clone --recursive [URL Git Repo]` | Clone repository that contain git submodule |
| `git submodule update --init` | Clone all submodule from remote repository |
| `git submodule add -b [branch] [URL Git Repo]` | Add submodule from remote repository and define [branch]|
| `git submodule init`| Initialize git submodule |
| `cd [submodule directory]` | Go to submodule directory |
| `git submodule deinit -f path/to/submodule` | Remove submodule |
