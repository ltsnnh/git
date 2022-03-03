
# <span style="color:Tomato">Git Cheat Sheet</span>

[![Git Logo](https://live.staticflickr.com/65535/51913894456_588b836c2b_c.jpg "Git")](https://flic.kr/p/2n6shaN)

## <span style="color:Orange">Index</span>

- [Set up](#set-up)
- [Init](#init)
- [Stage](#stage)
- [Unstage](#unstage)
- [Inspect & Compare](#inspect-&-compare)
- [Branches & Tags](#branches-&-tags)
- [Merge & Rebase](#merge-&-rebase)
- [Undo](#undo)
- [Update & Publish](#update-&-publish)
- [Sub-Module](#sub-module)
- [Git Flow](#git-flow)

### <span style="color:DodgerBlue">Set up</span>

Configuring user information used across all local repositories

	git config --global user.name “[user-name]”

	git config --global user.email “[valid-email]”

	git config --global color.ui auto

Show current configuration

	git config --list

### <span style="color:DodgerBlue">Init</span>

Clone an existing repository (via SSH/HTTP)

	git clone [--recursive] [url]

Initialize an existing directory as a Git repository

	git init [dir]

### <span style="color:DodgerBlue">Stage</span>

Changes in **working directory**

	git status

Add current changes to the next commit (**working directory** → **staging area**)

	git add [file]

Commit your staged content with message (**staging area** → **git repository**)

	git commit [file] -m "[message]"

### <span style="color:DodgerBlue">Unstage</span>

Discard changes in **working directory**

	git restore [file]

Unstage (**working directory** ← **staging area**)

	git restore --staged [file]

### <span style="color:DodgerBlue">Inspect & Compare</span>

Show difference (**working directory**, **staging area**)

	git diff [file]

	git diff --staged [file]

Show commit history (**git repository**)

	git log

	git log --follow [file]

Show any object in Git in human-readable format (**git repository**)

	git show [SHA]

Show commit history in GUI (**git repository**)

	gitk

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

[![Basic Remote Workflow](https://live.staticflickr.com/65535/51912929657_c43e3b4cbe_c.jpg "Workflow")](https://flic.kr/p/2n6nknk)