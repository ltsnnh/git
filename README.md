# <span style="color:Tomato">Git And Git Flow Cheat Sheet</span>
---
![Git Logo](https://raw.githubusercontent.com/arslanbilal/git-cheat-sheet/master/Img/git-logo.png)
---
## <span style="color:Orange">Index</span>
- [Set up](#set-up)
- [Configuration file](#configuration-file)
- [Create](#Create)
- [Local Changes](#local-changes)
- [Search](#search)
- [Commit History](#commit-history)
- [Branches & Tags](#branches-&-tags)
- [Merge & Rebase](#merge-&-rebase)
- [Undo](#undo)
- [Update & Publish](#update-&-publish)
- [Sub-Module](#sub-module)
- [Git Flow](#git-flow)
---
### <span style="color:DodgerBlue">Set up</span>
#### Show current configuration:
	$ git config --list
---
### <span style="color:DodgerBlue">Configuration file</span>
---
### <span style="color:DodgerBlue">Create</span>
#### Clone an existing repository (via SSH/HTTP):
	$ git clone [--recursive] <link>
#### Create a new local repository in the current directory <or a specific directory\>:
	$ git init <directory>
---
### <span style="color:DodgerBlue">Local Changes</span>
#### Changes in working directory:
	$ git status
#### Add all current changes to the next commit:
	$ git add .
#### Add some changes in <file\> to the next commit:
	$ git add -p <file>
#### Add only the mentioned files to the next commit:
	$ git add <file1> <file2>
#### Commit <file\> with message:
	$ git commit <file> -m 'message here'
#### Changes to tracked files <or of a specific file\>:
	$ git diff <file>
---
### <span style="color:DodgerBlue">Search</span>
---
### <span style="color:DodgerBlue">Commit History</span>
#### Show all commits, starting with newest:
	$ git log
#### Show various types of objects:
	$ git show <id-commit>
#### Show all commits in GUI:
	$ gitk
---
### <span style="color:DodgerBlue">Branches & Tags</span>
#### List all local branches:
	$ git branch
#### Create and switch new branch:
	$ git checkout -b <branch>
#### Switch HEAD branch:
	$ git checkout <branch>
#### Delete a local branch:
	$ git branch -d <branch>
---
### <span style="color:DodgerBlue">Merge & Rebase</span>
#### Merge branch into your current HEAD:
	$ git merge <branch>
---
### <span style="color:DodgerBlue">Undo</span>
#### Discard changes in a specific file in Working Directory:
	$ git restore <file>
#### Unstage a specific file in Staging Area:
	$ git restore --staged <file>
#### Reset your HEAD pointer to a previous commit and | all changes in Working Dir | all changes in Staging Area | discard all changes since then | :
	$ git reset --soft <id-commit>
	$ git reset --mixed <id-commit>
	$ git reset --hard <id-commit>
#### Revert a commit (by producing a new commit with contrary changes):
	$ git revert <id-commit>
#### Amend with last commit
	$ git commit --amend -m 'New message'
	$ git push --force-with-lease <repository> <branch>
---
### <span style="color:DodgerBlue">Update & Publish</span>
#### Add new remote repository, named <remote>:
	$ git remote add <remote> <url>
#### List all current configured remotes:
	$ git remote -v
#### Publish local changes | (first time):
	$ git push
	$ git push -u <remote> <branch>
#### Get all changes to local repository:
	$ git pull
#### Remove a folder from git tracking (Add the folder path to .gitignore file):
	$ git rm -r --cached <path_folder>
---
### <span style="color:DodgerBlue">Sub-Module</span>
#### Initialize a submodule:
	$ git submodule add <repository> <path>
#### Update a submodule \| all submodules:
	$ git submodule update [--init]
	$ git submodule foreach git pull <remote> <branch>
---
### <span style="color:DodgerBlue">Git Flow</span>
---
![Basic Remote Workflow](https://maitroisang.files.wordpress.com/2017/09/basic-remote-workflow.png)