# Navigating files and folders

## Folders (directories)

```
mkdir <path/name>              # make directory
rmdir <path/name>              # remove directory (if empty)

```

## EXERCISE

Break into groups and tackle the following questions:

* Do I have to be *in* a directory `dirA` to create another directory
  `dirB` inside `dirA`?
  
* What's the golfiest way to make the nested tree
  `cmdlinewkshp/day1/folder_exercise`?  *HINT:* read the `man`
  page!
  
* **Challenge:** now, given everything that's gone on so far, delete
  all those directories in as few keystrokes as you can (ABG!)


## Files

### Poor man's empty file creator

```
touch <name>                   # make an empty file called <name>
```

But not *really* what `touch` does...

### Linux is case-sensitive!

```shell
$ touch MyFile # This is not the same as...
$ touch myfile # ...this other thing.
```

### Other file-related commands
```
rm                             # remove the file
rm -r <dir>                    # remove a nonempty directory and its contents
cp file1 file2                 # create a copy of file1 named file2 (can use paths)
cp -r <path/dir> .             # copy <path/dir> to the current directory
mv <path/name> <path2/name2>   # move <path/name> to <path2/name2>
mv <path/name> <path2/name2>   # rename <path/name> to <path2/name2>
```

## Globbing -- matches *filenames* or *folders* only

```
*       # Zero or more characters
?       # Exactly one character
[abc]   # Exactly one of a,b,c
```

This can be combined with `ls` to simplify life considerably...

## `nano` text editor
