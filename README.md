# <span style="color:Tomato">Git Cheat Sheet</span>

[![Git Logo](https://live.staticflickr.com/65535/53127315515_e6b5a014eb_o.png "Git")](https://flic.kr/p/2oWFnYx)

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
- [Resolve Conflict (method: Rebase)](#resolve-conflict-method-rebase)
- [Resolve Conflict (method: 3-way merge)](#resolve-conflict-method-3-way-merge)
- [Git Flow](#git-flow)

### <span style="color:DodgerBlue">Set up</span>

Configure user information used across all local repositories

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

    git add [files]

Commit your staged content with message (**staging area** → **git repository**)

    git commit [files] -m "[message]"

### <span style="color:DodgerBlue">Unstage</span>

Discard changes in **working directory**

    git restore [files]

Unstage (**working directory** ← **staging area**)

    git restore --staged [files]

### <span style="color:DodgerBlue">Inspect & Compare</span>

Show commits in the current branch’s history (**git repository**)

    git log

    git log --follow [files]

Show any object in Git in human-readable format (**git repository**)

    git show [SHA]

Show difference (**working directory**, **staging area**)

    git diff [files]

    git diff --staged [files]

Show commit history in GUI (**git repository**)

    gitk

### <span style="color:DodgerBlue">Branch & Merge</span>

List all branches

    git branch

Create a new branch at the current commit

    git branch [branch]

Delete a local branch

    git branch -D [branch]

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

    git push [alias] [branch]

Fetch and merge any commits from the tracking remote branch

    git pull

Fetch down a branch from that Git remote

    git fetch [alias] [branch]

### <span style="color:DodgerBlue">Sub-Module</span>

Initialize a submodule

    git submodule add [repository [path]

Update (a) submodule(s)

    git submodule update [--init]

    git submodule foreach git pull [remote] [branch]

### <span style="color:Violet">Resolve Conflict (method: Rebase)</span>

step 1:

    git checkout [master]

    git pull [alias] [master]

step 2:

    git checkout [branch-be-conflicted]

    git rebase [master]

step 3: Resolve conflicted files manually and do

    git add [conflicted-files]

    git rebase --continue

step 4:

    git push [alias] [branch-be-conflicted] -f

### <span style="color:Violet">Resolve Conflict (method: 3-way merge)</span>

step 1:

    git checkout [master]

    git pull [alias] [master]

step 2:

    git checkout [branch-be-conflicted]

    git merge [master]

step 3: Resolve conflicted files manually and do

    git add [conflicted-files]

    git commit -m [conflicted-files] "[message]"

step 4:

    git push [alias] [branch-be-conflicted]

### <span style="color:DodgerBlue">Git Flow</span>

[![Basic Remote Workflow](https://live.staticflickr.com/65535/53127118219_2d860b6f94_o.png "Workflow")](https://flic.kr/p/2oWEnjT)
