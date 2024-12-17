# <span style="color:Tomato">The Git Guide</span>
![Git Logo](https://live.staticflickr.com/65535/53127315515_e6b5a014eb_o.png "Git")
## <span style="color:Orange">Index</span>
1. [About Git](#about-git)
1. [Git Basics](#git-basics)
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
The mechanism that Git uses for this checksumming is called a SHA-1 *hash* (a 40-character string) looks like this:
> 24b9da6552252987aa493b52f8696cd6d3b00373

In fact, Git stores everything in its database not by file name but by the *hash* value of its contents.
#### The Three States
![Three States](https://live.staticflickr.com/65535/54210396669_74b1f0ab04_z.jpg "Three states")
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
#### <span style="color:Green">Getting a Git Repository</span>
##### Initializing a Repository in an Existing Directory
    $ git init
This creates a new subdirectory named **.git** that contains all of your necessary repository files —
a Git repository skeleton.
##### Cloning an Existing Repository
    $ git clone <url>
#### <span style="color:Green">Recording Changes to the Repository</span>
##### Checking the Status of Your Files
    $ git status
##### Tracking New Files / Staging Modified Files
    $ git add [<files>...]
##### Ignoring Files
Often, you’ll have a class of files that you don’t want Git to automatically add or
even show you as being untracked, setting up a **.gitignore** file.
##### Viewing Your Staged and Unstaged Changes
    $ git diff
That command compares what is in your *working directory* with what is in your *staging area*.

    $ git diff --staged
This command compares your *staged* changes to your *last commit*.
##### Committing Your Changes
Now that your staging area is set up the way you want it, you can commit your changes.

    $ git commit -m "reminder of what you’ve modified"
You can see that the commit has given you some output about itself:  
which *branch* you committed to , what *SHA-1 checksum* the commit has,  
how many files were changed, and statistics about lines added and removed in the commit.
##### Removing Files
    $ git rm [<files>...]
##### Moving Files
    $ git mv <file_from> <file_to>
