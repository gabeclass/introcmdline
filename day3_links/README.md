# Links


## Symoblic ("soft") links

In GUI environments like what you find in Windows or macOS, you're
able to create an icon (that typically has a little arrow somewhere in
the image) which, when clicked, takes you to another file or folder.
These icons are often called **"shortcuts"**; a common use-case is to
make it easy to get from, say, your Desktop to some other file or
folder that's buried several levels away in the filesystem.

In Linux/Unix systems, these shortcuts are called **symbolic links**
or **_soft_ links** (we'll see what a *hard* link is in a minute), and
you generate them with the `ln` command.  There are a few syntaxes,
all pretty easy to glean from the `man` page for `ln`.  Let's give
that a shot...

### Exercise

Make a directory called `realfiles`, and make a text file in there
called `thisisreal.txt` that contains the single line of text: "This
is real".  Then, in your home folder, make the following symbolic
links (**REMEMBER TO USE THE `-s` FLAG!**):

* a link called `thisisfake.txt` which points to `thisisreal.txt`
* a "folder link" called `fakefiles` which points to the folder
  `realfiles`
  
  
And then let's practice doing various standard operations via the
links, e.g. `cd`ing, `cat`ing, `ls`ing, etc.

## Hard links

As we have already seen, files and folders are an illusion to make the
data on physical media like hard drives accessible to us in the
human-friendly file-cabinet motif.

A **hard link** is just an anchor from a piece of data on the hard
disk into the filesystem.  The neat thing is that a single piece of
data can be anchored to multiple locations in the filesystem, and all
these copies act as mirror images of one another (modify one, and
they're all modified).

### QUESTION

What do you think the `rm` command *really* does?
