# Streams

Linux has 3 core *file streams*:
* `stdin`  --> defaults to keyboard (abbrev 0)
* `stdout` --> defaults to screen (abbrev 1)
* `stderr` --> defaults to screen (abbrev 2)

But any of these "hoses" can be redirected to point to a file (this is
possible because, under the hood, Linux represents *everything* to the
user -- even hardware like the monitor or keyboard -- as if it were a
file)

# Redirection operators

```
>                              # redirect stdout to a file (clobbers)
1>                             # same as above
>>                             # redirect stdout to a file (appends)
2>                             # redirect stderr to a file (clobbers)
2>&1                           # redirect stderr to wherever stdout is
                               # (order of redirections matters!)
```

# Pipes

Many Linux commands and utilities are designed to take input from
`stdin` (when not otherwise specified) and sent output to `stdout`
(when not otherwise specified).  The pipe operator `|` is placed
between two commands that sit on a single line (each command gets its
own `stdin` and `stdout` "hose"), and the `stdout` hose of the command
on the left gets plugged into the `stdin` hose of the command on the
right.

For example:
```
$ cat file1 file2 | head | tail
```

## Some useful text filtering utilities that work this way

```
cat
tac
head
tail
tr
wc
uniq
sort
comm
cut
```


## Declaration of Independence pipeline exercise

Produce a histogram of the top 10 unique words in the US Declaration
of Independence, using the file `usdec.txt` you now have locally
stored, but **doing it all in a single pipeline!** This will take some
thought and some time.

