# Navigating the filesystem

## Some commands

```
whoami                         # who you are
pwd                            # print working directory
cd                             # used to change directory
ls                             # list directory contents (plus other uses)
du                             # show disk usage
tree                           # You'll see.... (don't type this yet!)
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
far that have special meaning to the bash shell.  Take about 5
minutes.


## Intro to options: examples with the `ls` command

Commands can generally be followed by one or more **options** and sometimes **arguments** (and sometimes the options themselves can have arguments).  Let's see some examples:
```shell
$ ls -a
$ ls -l
$ ls -t
$ ls -lh # You can combine options
```

## A taxonomy of "commands"

```
type <command>                 # what kind of 'verb' is <command>
```

The four categories of "verbs" in `bash`:
1. Aliases
2. Shell functions (`bash` is a full-featured programming language,
   and it allows users to define functions; these are beyond our scope
   today)
3. Shell builtins
4. Files (more precisely, executable files -- how does `bash` know
   where those files live?  Answer:  our old friend `PATH`

To see which category a command falls into, use `type`:

``` shell
$ type <command>               # shows type of <command>
$ type -a <command>            # shows all types when there's more
                               # than 1 version of <command>
```

Check the types of each of the following: `echo, pwd, cd, whoami,
ls`.  Then do it with `-a`.

> **FUN FACT:** You can "escape" an alias with a backslash.  Try:
> ```shell
> $ \ls
> ```

## Getting information or help

Let's look more into `ls`.  Can `ls` take arguments?  If so, how does
that work?

### `man` (i.e. manual) pages
```
man <command>                  # displays the manual page for <command>

```
It's important to understand the general *anatomy* of a command. The
top of a `man` page explains it for any given command.  Which command
were we typing in the last few examples?  How does it actually work?

Let's look at the `man` page for `ls`...

### Navigating `man` pages (`less` -- a pagination program)
`man` pages are really displayed using `less`:
```
less <file>                    # paginate thru file
```

Typing an `h` while in `less` (or while in a `man` page) brings up a
list of navigation commands (and other commands). Type `q` to quit the
`less` help menu (or `q` once out of the help menu to quit `less`
altogether).


### Beyond `man`

What if you can't find a `man` page for something?

```
help <builtin>           # gives info on bash builtin commands
apropos <string>         # lists man pages potentially pertinent to <string>
info <command>           # lists additional information about <command>

```
Sometimes, the help accessible via the shell is nonexistent or not
helpful.  That's when you Google.


## EXERCISE -- Slim Shady on many lines

Take a few minutes to read the man page for `echo` and see if you can
figure out how to get the Slim Shady text on multiple lines using a
single `echo` command but without using ANSI-C quoting.


## Extra-credit manpage exercise (for homework)

```
who                            # shows users that are logged on
```


Type:
```shell
$ who am i
```
Huh -- not quite the same as the output of `whoami`. What are the spaces doing?

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
Ah.  What's really going on?  The answer lies within the `man` page
(but takes some detective work to uncover).

