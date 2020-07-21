# Grabbing remote files

Two common utilities for grabbing remote files are `curl` and `wget`.  They work fairly similarly, except that

* `curl` is more like `cat` (which we'll meet soon) and dumps contents
  to the screen, while `wget` is more like `cp`;
  
* `curl` is better for one-off single-file downloads, while `wget` can
  operate *recursively* and fetch, e.g., a whole website and its
  folder structure; and
  
* `curl` is more universally installed across oeprating systems, while
  `wget` tends not be installed by default outside Linux (macOS, for
  instance, doesn't come with `wget` out of the box).
  
Let's see the differences in action...

### Exercise:

Make a directory called `sec1day1` and `cd` into it.  From there,
first use `curl` and then `wget` to grab the file at this URL: [Plain
text US Declaration of
Independence](https://web.math.princeton.edu/~perezgiz/usdec.txt)

What are the differences?

Note that you can make `curl` send output to a file instead of the
screen, and you can make `wget` send output to the screen instead of a
file.  **Manpage exercise: try to figure out how.**

# Tarballs

Now, using your tool of choice, (but **not** a browser!) go fetch this
file:
[sec1.tar.gz](https://web.math.princeton.edu/~perezgiz/sec1.tar.gz)

Let's learn how to extract this with the `tar` command...



### Exercise:

Make a folder called `testtar`, fill it with 100 empty files called
`fakefile001.txt`... `fakefile100.txt`, and then make a gzipped
tarball called `fakefiles.tar.gz` out of that whole folder.

