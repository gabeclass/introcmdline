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
The variable `PATH` contains a colon-delimited list of folders
(i.e. directories) found on the system.  We'll see later why this list
is here and how it is used.

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

Multiple commands can be issued on one line, separated by a `;`, like this:
```shell
$ echo $y
$ y=something; echo $y
# What happens?  Why?
```


Variable assignment can preface a command.  For instance:
```shell
$ echo $z
$ z=something echo $z
# What happens?  Why?
# Was z actually defined?  Let's see...
$ echo $z
# What if I instead type...
$ z=something echo $y
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

### Escaping \& Quoting

But what if you wanted to type a literal dollar sign? This works:
```shell
$ echo $

```
But this won't:
```shell
$ echo $HOME

```
In the latter case, we need to "turn off" the special meaning of the
`$`.  Doing that is called **escaping** a character.  There are a few
ways to do that in bash.  Here are a couple:

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

#### EXERCISE

How can you get a single backlash `\` with the shortest possible
command?  In how few characters do you think you can do it?

**CAVEAT** If some of you try something that causes the prompt to
change to a `>` character, then you uncovered something we'll deal
with in a minute.  If that happens, type `Ctrl-c` and you'll get back
to your regular prompt.


About that caveat... When you type the following lines, very different
things happen.  Let's understand why..
```shell
$ echo '\'
# What happens?
$ echo "\"
# What happens this time?
```

### The "secondary" bash prompt

Some bash commands can span several lines.  Whenever you're moved to a
second (or higher) line within a *single* command, bash will indicate
this by changing the prompt to a different character (the default for
this character is `>`, but as we'll see later in the workshop, this
can be customized).



### ANSI C Quoting

For certain characters, it is not obvious how you would type them
literally.  For instance, a newline -- suppose we wanted to get the
following output with a single `echo` command?

``` shell
My name is...
My name is...
My name is...
Slim Shady!
```

We will revisit this question again later and offer additional
solutions, but for now, try tools you've seen so far, and you'll see
that they don't work (at least not without some extra tweaks that
we'll learn about later).  In particular, see what happens if you
escape a newline as you type (it doesn't work).

We can achieve this using an additional kind of quoting called "ANSI-C
Quoting". A `$` before a *single-quoted string* will parrot back the
string, except that it will replace so-called "backslash escape
sequences" as special ASCII characters.  The backslash-escape notation
for a newline is `\n`, so we could write:

``` shell
$ echo $'My name is...\nMy name is...\nMy name is...\nSlim Shady!'
```

#### Bash automatically concatenates adjacent strings

So we could also have done this (make sure you understand what's happened):

``` shell
$ echo My name is...$'\n'My name is...$'\n'My name is...$'\n'Slim Shady!
```

