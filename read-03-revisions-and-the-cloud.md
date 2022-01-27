# Outline Notes – Git Tutorial: A Comprehensive Guide


## Version Control
- system that allows revisiting of various of files or file sets with all changes recorded
- Local Version Control: outdated, when programmers used one hard disk database to store changes to files
- Centralized Version Control System (CVCS/CVS): single server storing all changes and version, accessible by various clients. Collaboration was streamlined giving team members more knowledge of each other’s file activities, and more control for revision privilege allocation by administrators
- Distributed Version Control Systems (DVCS): unlike CVS (with server as single point of failure), DVCS allows mirror repository creation with data backups that allow lost information to be replaced onto the server. Allows simultaneous workflows because programmers can use multiple mirrored repositories to collaborate with each other to complete joint projects.

## So, what is Git?
- Snapshots - each ‘commit’ is a changed version of the project, with file and reference to it stored.
- Local Operations - Git relies on local disk operations, which improves expediency by eliminating the need to fetch info history from the server, so programmers can keep working when offline.
- Tracking Changes - Git tracks all changes, detects file corruption or info loss in transit
- Loss of Data - Git greatly minimizes irreversible file damage like lost data, making it very difficult for committed file snapshot to be lost
#### States
- Committed - data is securely store in a local database
- Modified - file has been changed but not committed to the database
- Staged - flagged a file’s changed version to be committed in the next snapshot

## History of Git
- Roots in open source project Linux kernel, developers of which started using DVCS called BitKeeper in 2002
- 2005 - tension between Linux kernel community and company behind BitKeeper (over gratis status); many developers stopped using that DVCS
- Git creation consequently began by Linus Torvalds (chief architect of Linux kernel)
- Goal - create fast DVCS with similar workflow design to BitKeeper
#### Git:
- Allowed for non-linear development via multiple branches
- Supported large projects
- Possessed strong mechanisms to prevent corruption
- Had simple design
- Since 2005, has become the one of the most utilized VCSs in the world

## Getting Started
- Can be installed as a package, via another installer, or by downloading and compiling the source code
- Graphical Clients - Git uses inherent Graphical User Interface (GUI) tools, but users can utilize third-party tools instead

## Setting up a Git Repository
- Importing: to import into Git, do this in Terminal or Command Line:
- Switch to the target project’s directory (using `cd` to change directory)
- Use the `git init` command which creates new subdirectory named .git
- Type the following to perform an initial commit by typing:
```
git add *.c
git add LICENSE
git commit -m “any message here”
```
- Now your files are tracked.
#### Cloning: to create a copy of existing Git repository (include repository’s URL instead):
```
git clone https://github.com/test
```
- Cloning files copies all versions all project files

## Workflow
- Local Repository Structure: three components
1. Working Directory (where the actual files live)
2. Index (or staging area)
3. Head (which typically points to the most recent commit)
#### Saving Changes: files in working copy of project file are either
1. Tracked - can be modified, unmodified, or staged (part of latest commit)
2. Untracked - not staged, not part of latest commit

#### File Status Life Cycle
- Edited file is flagged by Git as modified due to changes since last commit
- You stage modified file
- You commit changes to modified file
- Check File Status using command `git status`
#### Track and Stage New File
- You can track one file only with command `git add filename`
- Or track all repo files with command `git add *`
- After either command, the files are tracked and staged
- To commit file: command `git commit -m “message about changes made”`
- To commit all changes: command `git commit -a`
- To push changes to repository: `git push origin master`
- To stash changes (when you’re not ready to commit them but you don’t want to lose them) use command `git stash` to remove hide them away until later, and then when you want to retrieve changes use command `git stash apply`

## Remote Repositories
- These are versions of a project (living either online or on a network) which one can either push data to or pull from
- Cloned repositories automatically refer to the ‘from’ server and the local branch as “origin” and “master”, respectively
- Seeing Your Remotes: run command `git remote` to view short names, or use `git remote -v`
