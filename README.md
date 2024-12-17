# <span style="color:Tomato">The Git Guide</span>
![Git Logo](https://live.staticflickr.com/65535/53127315515_e6b5a014eb_o.png "Git")
## <span style="color:Orange">Index</span>
1. [About Git](#about-git)
1. [Git Basics](#git-basics)
1. [Resolve Conflict (method: Rebase)](#resolve-conflict-method-rebase)
1. [Resolve Conflict (method: 3-way merge)](#resolve-conflict-method-3-way-merge)
### <span style="color:DodgerBlue">About Git</span>
#### Distributed Version Control Systems
Every clone is really a full backup of all the data.
#### Stream of snapshots
Every time you commit, or save the state of your project,
Git basically takes a picture of what all your files look like at that moment and
stores a reference to that snapshot.  
To be efficient, if files have not changed, Git doesn’t store the file again,
just a link to the previous identical file it has already stored.
#### Git Has Integrity
Everything in Git is checksummed before it is stored and is then referred to by that checksum.  
The mechanism that Git uses for this checksumming is called a SHA-1 hash (a 40-character string) looks like this:
> 24b9da6552252987aa493b52f8696cd6d3b00373

In fact, Git stores everything in its database not by file name but by the hash value of its contents.
#### The Three States

#### First-Time Git Setup
You can view all of your settings and where they are coming from using:

    $ git config --list --show-origin
#### Your Settings
    $ git config --global user.name "Ltsnnh"
    $ git config --global user.email lt.anh197@gmail.com
    $ git config --global core.editor code
    $ git config --global init.defaultBranch main
#### Getting Help
    $ git <verb> --help
### <span style="color:DodgerBlue">Git Basics</span>
If you can read only one chapter to get going with Git, this is it.







### <span style="color:DodgerBlue">Sub-Module</span>

Initialize a submodule

    git submodule add [repository] [path]

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
