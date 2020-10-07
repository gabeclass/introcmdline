# Permissions


## Anatomy of Permissions
Here's an example `ls -al`:
```
[perezgiz@adroit4 ~]$ ls -al
total 784
drwx------.   12 perezgiz pustaff   4096 Oct 28 05:22 .
drwxr-xr-x. 1668 root     root     40960 Oct 28 08:57 ..
-rw-r--r--.    1 perezgiz pustaff 239362 Oct 10 18:20 10oct19.script
-rw-r--r--.    1 perezgiz pustaff  49471 Oct 10 18:20 10oct19.timing
-rw-------.    1 perezgiz pustaff   6862 Oct 28 05:49 .bash_history
-rw-r--r--.    1 perezgiz pustaff     18 Sep 13  2018 .bash_logout
-rw-r--r--.    1 perezgiz pustaff    193 Sep 13  2018 .bash_profile
-rw-r--r--.    1 perezgiz pustaff    231 Sep 13  2018 .bashrc
drwx------.    4 perezgiz pustaff     51 Sep 25 04:23 .cache
drwx------.    3 perezgiz pustaff     33 Sep 25 04:23 .dbus
-rw-r--r--.    1 perezgiz pustaff    334 Sep 13  2018 .emacs
drwx------.    2 perezgiz pustaff     10 Sep 25 04:24 .emacs.d
drwxr-xr-x.    2 perezgiz pustaff    186 Oct 25 12:58 hw2
drwxr-xr-x.    2 perezgiz pustaff    178 Oct 10 18:08 introlinux
-rw-r--r--.    1 perezgiz pustaff    172 Sep 13  2018 .kshrc
-rw-------.    1 perezgiz pustaff     43 Oct 10 16:53 .lesshst
drwxr-xr-x.    3 perezgiz pustaff     27 Oct 17 14:53 .local
drwxr-xr-x.    6 perezgiz pustaff    101 Sep 25 04:23 .mozilla
drwxr-xr-x.    3 perezgiz pustaff     26 Aug 26 16:11 ondemand
drwxr-----.    3 perezgiz pustaff     27 Aug 26 16:09 .pki
drwx------.    2 perezgiz pustaff     60 Oct 17 14:48 .ssh
-rw-r--r--.    1 perezgiz pustaff 389617 Oct 17 14:53 usc.pdf
-rw-------.    1 perezgiz pustaff    106 Oct 17 15:05 .Xauthority
-rw-r--r--.    1 perezgiz pustaff    658 Sep 13  2018 .zshrc
[perezgiz@adroit4 ~]$ 
```

The first several columns pertain to the file permissions. `d`
indicates a directory. `-` indicates a file.

Let's focus on one file first:
```
-rw-r--r--.    1 perezgiz pustaff 239362 Oct 10 18:20 10oct19.script
```


After the first `-`, you see three batches of three "switches" each.
Each switch can be "on" or "off". Each batch of switches is `rwx`.
When a switch is on, you see the corresponding letter; when a switch
is off, you see a `-`.

These switches represent permissions for the **user** (the first user
of the two names listed -- this person owns the file), the **group**
(the second name listed -- each file is associated to one primary
group), and **other** (everyone else, on this same system or out on
the internet).

So in this case, I alone (or the root user!) can read and write this
file. My group (`pustaff`) can read it, and every other logged in user
can also read it. `x` permissions mean that file can be *executed*
(for instance, check out the permissions on `/bin/ls`, which is a
*program*).

For folders, permissions mean something different:
```
drwxr-xr-x.    2 perezgiz pustaff    178 Oct 10 18:08 introlinux
```
* `r` -- you can see the contents of that folder, i.e. `ls` it
* `w` -- you can change the contents (add or delete files)
* `x` -- you can enter the folder (`cd` into it), and access files
  within the folder even without `cd`ing into it

## `chmod`
You can change permission states using the command `chmod`. `touch` a file named `test.txt`,
then `ls -al test.txt`:
```
-rw-r--r--. 1 perezgiz pustaff 0 Oct 28 09:23 test.txt
```

Say I wanted to let my group write it, I'd use `chmod` with some flags
to make that happen.

`chmod g+w test.text` will make it readable by its assigned group.

`chmod g=rw test.text` would do the same thing, by stating what you
want the final permissions to be (read permission, which the group
already has, and also write permission).

`chmod g-w test.text` would take that away.


The syntax is roughly: `chmod <ugo><+-=><rwx> path/to/file.txt` `u` is
user, `g` is group, `o`is other. `+` or `-` add/remove permissions and
`r` is read, `w` is write, and `x` is write.

To specify permissions for, say, the user *and* the group, you
comma-separate the assignments: `chmod g=rw,o=r test.text # The u,g,o
permissions can be given in any order`

You can also specify the permissions using 'octal' permissions like
`chmod 777` which are shorthand ways to specify the final permission
state directly, rather than the change (treat each letter in a `rwx`
batch as a bit in a 3-bit number that can run from 0-7).

## Advancec permissions: Access Control Lists (ACLs)

What if you only want certain specific users to be able to access a
file? Or only users in certain groups (the group permissions you see
for the file `ls -al` will control access for the "primary" group
associated with that file at the time of its creation, but you the
file owner may belong to more than one group and may want some of
those groups to access a file or folder but not others)?

For these purposes, most Linux filesystems (including the ones on our
clusters) support an additional finer-grained layer of file/folder
permissions called Access Control Lists (ACLs).  How they work goes
beyond the scope of this workshop, but if you'd like to learn more,
here is [an overview of ACLs from Red
Hat](https://www.redhat.com/sysadmin/linux-access-control-lists).

