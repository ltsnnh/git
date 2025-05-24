# <span style="color:Tomato">The Git Guide</span>
![Git Logo](https://live.staticflickr.com/65535/53127315515_e6b5a014eb_o.png "Git")
## <span style="color:Orange">Index</span>
1. [About Git](#about-git)
1. [Git Basics](#git-basics)
### <span style="color:DodgerBlue">About Git</span>
#### Distributed Version Control Systems
Every clone is really **a full backup** of all the data.
#### Stream of snapshots
Every time you commit, or save the state of your project,
Git basically takes a picture of what all your files look like at that moment and
stores a reference to that snapshot.  
To be efficient, if files have **not changed**, Git doesn’t store the file again,
just a **link to the previous identical file** it has already stored.
#### Git Has Integrity
Everything in Git is checksummed before it is stored and is then referred to by that checksum.  
The mechanism that Git uses for this checksumming is called a **SHA-1 hash** (a 40-character string) looks like this:
> 24b9da6552252987aa493b52f8696cd6d3b00373

In fact, Git stores everything in its database not by file name but by the **hash** value of its contents.
#### The Three States
![Three States](https://live.staticflickr.com/65535/54210396669_74b1f0ab04_z.jpg "Three states")
#### First-Time Git Setup
Git comes with a tool called `git config` that lets you set configuration variables that control all how Git operates.  
These variables can be stored in three different places:  
1. ***[path]/etc/gitconfig*** file: values applied to every user on the system, if you pass the option `--system` to `git config`  
2. ***~/.gitconfig*** file: values specific personally the user, if you pass the option `--global` to `git config`  
3. ***.git/config*** file in the Git directory: values specific personally the user, if you pass the option `--local` to `git config`  

Each level overrides values in the previous level.  
You can view all of your settings and where they are coming from using:  

    $ git config --list --show-origin
#### Your Identity
    $ git config --global user.name "Ltsnnh"
    $ git config --global user.email lt.anh197@gmail.com
#### Your Editor
    $ git config --global core.editor <editorname>
#### Getting Help
Get full-blown manpage help:  

    $ git <verb> --help
Get a quick refresher on the available options for a Git command:  

    $ git <verb> -h
### <span style="color:DodgerBlue">Git Basics</span>
If you can read only one chapter to get going with Git, this is it.
#### <span style="color:Green">Getting a Git Repository</span>
##### Initializing a Repository in an Existing Directory
    $ git init
This creates a new subdirectory named ***.git*** that contains all of your necessary repository files — a Git repository skeleton.
##### Cloning an Existing Repository
    $ git clone <url>
#### <span style="color:Green">Recording Changes to the Repository</span>
##### Checking the Status of Your Files
    $ git status
##### Tracking New Files / Staging Modified Files
    $ git add [<files>...]
##### Ignoring Files
Often, you’ll have a class of files that you don’t want Git to automatically add or
even show you as being untracked, setting up a ***.gitignore*** file.
##### Viewing Your Staged and Unstaged Changes
See what you’ve changed but not yet staged.  
The command compares what is in your *working directory* with what is in your *staging area*.

    $ git diff
See what you’ve staged that will go into your next commit.  
The command compares what is in your *staging area* with what is in your *last commit*.  

    $ git diff --staged
##### Committing Your Changes
Now that your staging area is set up the way you want it, you can commit your changes.

    $ git commit -m 'reminder of what you’ve modified'
You can see that the commit has given you some output about itself:  
which **branch** you committed to , what **SHA-1 checksum** the commit has,  
how many files were changed, and statistics about lines added and removed in the commit.
##### Removing Files
    $ git rm [<files>...]
##### Moving Files
    $ git mv <file_from> <file_to>
#### <span style="color:Green">Viewing the Commit History</span>
    $ git log
Add a nice little ASCII graph showing your branch and merge history.

    $ git log --graph
#### <span style="color:Green">Undoing Things</span>
If you want to redo the lastest commit, make the additional changes you forgot, stage them, and commit again using the `--amend` option:

    $ git commit --amend
Only amend commits that are still local and have not been pushed somewhere.
##### Unstaging a Staged File
    $ git restore --staged <file>
##### Unmodifying a Modified File
    $ git restore <file>
#### <span style="color:Green">Working with Remotes</span>
To see which remote servers you have configured:

    $ git remote
If you’ve cloned your repository, you should at least see origin — that is the default name Git gives to the server you cloned from.  
Shows the URLs that Git has stored for the shortname to be used when reading and writing to that remote:

    $ git remote -v
##### Adding Remote Repositories
To add a new remote Git repository as a shortname you can reference easily:

    $ git remote add <shortname> <url>
##### Fetching and Pulling from Your Remotes
    $ git fetch <remote>
The `git fetch` command only downloads the data to your local repository —
it doesn’t automatically merge it with any of your work or modify what you’re currently working on.  
You have to merge it manually into your work when you’re ready.  
If your current branch is set up to track a remote branch,
you can use the `git pull` command to automatically fetch and then merge that remote branch into your current branch.
##### Pushing to Your Remotes
    $ git push <remote> <branch>
##### Inspecting a Remote
    $ git remote show <remote>
#### <span style="color:Green">Tagging</span>
##### Listing Your Tags
    $ git tag
    $ git tag -l "*string_to_match"
##### Creating Tags
Git supports two types of tags: *lightweight* and *annotated*.
###### Annotated Tags
    $ git tag -a <tagname> -m <'message'>
###### Lightweight Tags
    $ git tag <tagname>
##### See Information of Tags
    $ git show <tagname>
##### Tagging Later
    $ git tag -a <tagname> <SHA-1 hash>
##### Sharing Tags
By default, the `git push` command doesn’t transfer tags to remote servers.  
You will have to explicitly push tags to a shared server after you have created them.

    $ git push <remote> <tagname>
For all tags:

    $ git push <remote> --tags
For all *annotated tag*:

    $ git push <remote> --follow-tags
##### Deleting Tags
    $ git tag -d <tagname>
Note that this does not remove the tag from any remote servers.  
For deleting a tag from a remote server.

    $ git push origin --delete <tagname>
##### Checking out Tags
    $ git checkout <tagname>
