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

# Startup file (.bashrc)

All of these can be customized and set when your shell begins by
placing the `export` commands in a file called `.bashrc` in your home
folder.

Other useful customizations can go in this file.  Like aliases (or, if
you choose to do a deeper dive, `bash` functions). For instance,
here's a useful alias to just show you the folders inside your working
directory:
```shell
alias lsd='ls -d */'
```
Can you read the `man` page for `ls` to understand why this works?

## Reloading your .bashrc

If you edit your `.bashrc`, it won't take effect in the current shell
session unless you rerun it, using the command `source`:
```shell
$ source ~/.bashrc
```
