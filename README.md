
# <span style="color:Tomato">Git Cheat Sheet</span>

[![Git Logo](https://live.staticflickr.com/65535/51913894456_588b836c2b_c.jpg "Git")](https://flic.kr/p/2n6shaN)

## <span style="color:Orange">Index</span>

- [Set up](#set-up)
- [Init](#init)
- [Stage](#stage)
- [Unstage](#unstage)
- [Inspect & Compare](#inspect-&-compare)
- [Branch & Merge](#branch&-merge)
- [Reset](#reset)
- [Push & Pull](#push-&-pull)
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

Show commits in the current branch’s history (**git repository**)

	git log

	git log --follow [file]

Show any object in Git in human-readable format (**git repository**)

	git show [SHA]

Show commit history in GUI (**git repository**)

	gitk

### <span style="color:DodgerBlue">Branch & Merge</span>

List all branches

	git branch

Create a new branch at the current commit

	git branch [branch-name]

Delete a local branch

	git branch -d [branch]

Switch to another branch

	git checkout [branch]

Merge the specified branch’s history into the current one

	git merge [branch]

### <span style="color:DodgerBlue">Reset</span>

Reset your HEAD pointer to a specified commit and put at

**staging area**

	git reset --soft <SHA>

**working directory**

	git reset --mixed <SHA>

... and discard changes

	git reset --hard <SHA>

### <span style="color:DodgerBlue">Push & Pull</span>

Transmit local branch commits to the remote repository branch

	git push

Fetch and merge any commits from the tracking remote branch

	git pull

### <span style="color:DodgerBlue">Sub-Module</span>

Initialize a submodule

	git submodule add [repository [path]

Update (a) submodule(s)

	git submodule update [--init]

	git submodule foreach git pull [remote] [branch]

### <span style="color:DodgerBlue">Git Flow</span>

[![Basic Remote Workflow](https://live.staticflickr.com/65535/51912929657_c43e3b4cbe_c.jpg "Workflow")](https://flic.kr/p/2n6nknk)
