# Navigating the filesystem

## Some commands

```
whoami                         # who you are
pwd                            # print working directory
cd                             # used to change directory
ls                             # list directory contents (plus other uses)
du                             # show disk usage
```

## Absolute and relative pathnames

* Every folder on the system has an absolute "address" called its
  *absolute pathname*, beginning with the root directory `/` and
  descending through the file tree.  So, for instance, my home
  directory on Adroit has absolute pathname `/home/perezgiz`.

* If you enter a folder name that *does not* begin with `/`, the shell
  interprets that as a *relative pathname* (relative to where you are
  right now). In other words, the shell *prepends* the result of `$
  pwd` to what you've typed.

* The above also applies to *filenames*, not just to folder names.

* Shortcuts to refer to certain folders:
  ```
  .                              # where you are right now
  ..                             # the folder one level above you
  ~                              # *your* home folder (/home/<youruserID>)
  ~<user>                        # home folder of <user>
  ```

## EXERCISE: Catalog special characters so far

Break into groups and make a catalog of any characters we've seen so
far that have special meaning to the bash shell.  Take about 10
minutes.

## An experiment

Type:
```shell
$ who am i
```
Huh. What are the spaces doing?

What about:
```shell
$ who registered late
```

Or:
```shell
$ who smells funky
```

Last one:
```shell
$ who knows all this about me
```
Ah.  What's really going on?

## Getting information or help

```
man <command>                  # displays the manual page for <command>

```

It's important to understand the general *anatomy* of a command. The
top of a `man` page explains it for any given command.  Which command
were we typing in the last few examples?  What does it actually do?

```
who                            # shows users that are logged on
```

## Intro to options: examples with the `ls` command

Commands can generally be followed by one or more **options** and sometimes **arguments** (and sometimes the options themselves can have arguments).  Let's see some examples:
```shell
$ ls -a
$ ls -l
$ ls -t
$ ls -lh # You can combine options
```
Can `ls` take arguments?  If so, how does that work?

## Beyond `man`

What if you can't find a `man` page for something?

```
apropos <string>         # lists man pages potentially pertinent to <string>
info <command>           # lists additional information about <command>

```
Sometimes, the built-in help is nonexistent or not helpful.  That's when you Google.


## `less` -- a pagination program
```
less <file>                    # paginate thru file
```

`man` is really displayed with `less`


## BONUS -- a taxonomy of commands

```
type <command>                 # what kind of 'verb' is <command>
```

The four categories of "verbs" in `bash`:
1. Aliases
2. Shell functions (`bash` is a full-featured programming language;
   abeyond our scope today)
3. Shell builtins
4. Files (more precisely, executable files -- how does `bash` know
   where those files live?  Answer:  our old friend `PATH`


