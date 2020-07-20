# Some features of bash as a language

## The `echo` command

This is a useful command that parrots what you type back to the screen
```shell
$ echo Hello World
Hello World
```

## Variables

Compare what happens when you type the following commands:
```shell
$ echo HOME
$ echo $HOME
```
What's the difference? Bash variables!

Now try this one:
```shell
$ echo PATH
$ echo $PATH
```
The variable `PATH` contains a colon-delimited list of folders (i.e. directories) found on the system.  We'll see later why this list is here and how it is used.

How do you define your own variables?
```shell
$ echo $x
# Note what happens when a variable is not defined. No error...
$ x=something
$ echo $x
```


What if you had typed:
```shell
$ echo $y
$ y=something else
# What happens?  Why?
```

Variable assignment can preface a command.  For instance:
```shell
$ echo $y
$ y=something echo $y
# What happens?  Why?
```

You can clear out variable values with the `unset` command:
```shell
$ unset x
$ echo $x
```


## Taking notes / comments in bash

To add a note while on the command line, preface your note with the
`#` character.  You can do this on the whole line, or after a command
before hitting return.

```shell
$ #This is a commment, whole line is ignored
$ echo Hello #Everything from here on is ignored
Hello
$ # Output remained
```

## Brace expansion -- good for iterating like a `for` loop

Bash has some convenient shorthands that can be leveraged to great
effect.

```shell
$ echo b{a,e,i,o,u}d
bad bed bid bod bud
```

### Braces also know basic sequences (really ASCII + counting)

```shell
$ echo file{05..25}
# What happens?
```

What happens here?
```shell
$ echo file{05..25..3}
# What happens this time?
```

## Special characters

Apparently, certain characters in bash have a special meaning and are
not treated literally.  For instance, the `$` seems to mean "treat the
following string as the name of a variable and replace the whole
expression with the value of the variable".

### Escaping

But what if you wanted to type a literal dollar sign? This works:
```shell
$ echo $

```
But this won't:
```shell
$ echo $HOME

```
In the latter case, we need to "turn off" the special meaning of the `$`.  Doing that is called **escaping** a character.  There are a few ways to do that in bash.   Here are a couple:

* Preface the special character with a backslash
```shell
$ echo \$HOME

```
* Use *single* quotation marks (i.e. apostrophes, a.k.a. **ticks** in
  Linux-speak)
```shell
$ echo '$HOME'

```
What about double quotation marks?  Try these variants:
```shell
$ echo "$HOME"
$ echo '$'HOME
$ echo "$"HOME
# What happens?
```

