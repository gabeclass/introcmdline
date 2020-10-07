# Variables

Bash allows you to define variables.  You reference their values by
preceding them with a `$`:

```shell
$ j=3
$ echo j
j
$ echo $j
3
```

# Environment variables

Some variables are known to all commands you run and subshells you
spawn.  These are called *environment variables* (in ALL CAPS by
convention).

```
$ export <var>
# This promotes an existing variable to the environment
$ export <var>=<value>
# Defines a variable and exports it, all in one shot
```

* PATH -- controls where the system looks for executables

* PS1 -- controls your prompt

* EDITOR -- some programs, like git, use this to figure out your
  preferred default editor

# Startup files (.bash_profile and .bashrc)

## .bash_profile

Whenever you *log into* a system, a file (that must live in your home
folder) called `.bash_profile` gets run, assuming that file exists
(this file can contain legal lines of bash -- it's essentially a
script).  You could put lines in here that, for instance, customize
the value of your `PS1` and `PS2` variables to make them to your
liking (via export commands).

You could also define functions in here, customize other environment
variables like `PATH` and `EDITOR`, and set up aliases.  But it's more
common to put *those* customizations in a second file called
`.bashrc`, as explained below.

## .bashrc

`.bashrc` (which must also live in your home folder) gets run not when
you log in but whenever any *subshell* is spawned (e.g. when a script
is run, or when you run a command inside `( )`, or if you just
manually spawn a subshell by running `bash` on the command line.  Why?
Because you might want your functions and aliases and your
personalized `PATH` variable value to be available not just at the
main login shell but also to other programs or scripts you run that
get thrust into subshells.

So things like certain `export` commands and aliases commonly go into
`.bashrc`, and then to make those customizations also available in
your login shell, you have the final line of `.bash_profile` as

``` shell
source ~/.bashrc
```
so that `.bash_profile`'s last act is to run `.bashrc` "manually".

As an example, here's a useful alias you might want to add to
`.bashrc` (this shows you just the folders inside your working
directory):
```shell
alias lsd='ls -d */'
```
Can you read the `man` page for `ls` to understand why this works?

## Reloading your .bashrc

**NOTE:** If you edit your `.bash_profile` or `.bashrc`, the changes won't take effect in the current shell
session unless you rerun it, using the command `source`:
```shell
$ source ~/.bashrc
```

An alternate syntax for the `source` command is a single dot:
```shell
$ . ~/.bashrc
```
Note that this is a different usage of the dot than the one we've
already seen (as a reference to the current directory).  When a single
dot is the *first* token on a command line, bash interprets it as a
shorthand for the
command `source`.  Everywhere else on the command line, bash leaves
the dot character untouched so that the command on your command line
receives it as a literal dot (which is good, b/c as we've seen, there
is an extra file named literal-dot, i.e. `.`, in every folder which is
just a hard link to the current folder).
