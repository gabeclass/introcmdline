# Typing more easily in the shell

## Swap Caps Lock and left Ctrl on your laptop

On older UNIX keyboards, the `Ctrl` key used to sit where the `Caps
Lock` key does on contemporary keyboards today. That's why a lot of
keyboard shortcuts that UNIX had (and that Linux and the `bash` shell
and other common programs inherited) were based on frequently pressing
the left `Ctrl` key.

Unfortunately, today's laptop keyboards tend to put the left `Ctrl`
key down in the lower left corner of the laptop.  Attempting to press
it often requires an awkward contortion of the left hand that can lead
to a (painful) repetitive strain injury that many Linux/UNIX users
call "[emacs
pinky](https://www.emacswiki.org/emacs/RepeatedStrainInjury)".

For full desktop keyboards, there are lots of options around
that can make pressing the left `Ctrl` key often more natural and
ergonomic.  But for laptop keyboards, there are fewer remedies.  The
most common is to *remap* the `Caps Lock` key to behave like `Ctrl`
(and then, if you still want access to a `Caps Lock` key, also remap
the left `Ctrl` key to behave like `Caps Lock`).

This *swapping* of `Caps Lock` and `Ctrl` takes a few hours or days to
get used to, especially if you look at your hands and keys a lot when
you type (if this sounds like you, it might be worth putting a small
piece of masking tape with `Ctrl` written on it in marker over your
`Caps Lock` key until the "muscle memory" in your hands adjusts). But
it will have a profound impact on your efficiency and comfort while
working on the command line, which especially for beginners can mean
the difference between abandoning the exercise and sticking with it &
growing.

Here are some instructions for how execute this key-swap, depending on
your operating system.  Many of the links below come from the
[emacswiki page dedicated to remapping
`Ctrl`](https://www.emacswiki.org/emacs/MovingTheCtrlKey), which has
instructions and screenshots for how to accomplish this in different
operating systems (including Android, apparently) and in different
desktop or non-windowed environments within Linux.

### macOS

* [Official instructions from
Apple](https://support.apple.com/guide/mac-help/change-the-behavior-of-the-modifier-keys-mchlp1011/mac).
Procedure is straightforward and takes about 30 seconds.

* Analogous instructions [from
  emacswiki](https://www.emacswiki.org/emacs/MovingTheCtrlKey#toc13).

### Linux

* [Instructions from
  emacswiki](https://www.emacswiki.org/emacs/MovingTheCtrlKey#toc2) if
  you run one of the major Linux desktop environments (GNOME, KDE,
  Xfce, etc).
  
* [Another useful
  article](https://opensource.com/article/18/11/how-swap-ctrl-and-caps-lock-your-keyboard)
  with instructions on how to swap `Caps Lock` and `Ctrl`.  If you
  find gaps (but are a Linux user), you can probably do some light
  googling to fill in any gaps in the information (just make sure
  you're reading a resource from within the past 2-3 years, to ensure
  you aren't reading dated information).

* If you want to modify the `xmodmap` file directly to achieve the
  same thing in a desktop environment, there some instructions in
  [this
  article](https://www.jveweb.net/en/archives/2010/11/making-better-use-of-the-caps-lock-key-in-linux.html#jveweb_en_017_03)
  (which is from 2011 but still basicall correct) and some from
  emacswiki on achieving this with
  [`xmodmap`](https://www.emacswiki.org/emacs/MovingTheCtrlKey#toc5)
  or with
  [`xkb`](https://www.emacswiki.org/emacs/MovingTheCtrlKey#toc6).

* emacswiki also has
  [instructions](https://www.emacswiki.org/emacs/MovingTheCtrlKey#toc7)
  on how to achieve a key swap on Linux systems that do *not* use a
  desktop or windowing environment (this will also give you the effect
  in the so-called "virtual consoles" accessible via the *function*
  keys even on Linux laptops that do run a desktop
  environment). keySimilar but more comprehensive instructions that
  detail how to do this both within the desktop GUI environment *and*
  within consoles that don't access a windowing system at all can be
  found on the [emacswiki page dedicated to remapping
  `Ctrl`](https://www.emacswiki.org/emacs/MovingTheCtrlKey).
  
### Windows

The key swap is most cumbersome on Windows because either you have to
edit the Windows Registry by hand (which can feel daunting to novices)
or you have to install extra software that presents a nicer interface
for key swapping.  emacswiki has details for current and older
versions of Windows
[here](https://www.emacswiki.org/emacs/MovingTheCtrlKey#toc14).

Luckily, Microsoft has now added [a nicer interface for managing the
keyboard
configuration](https://github.com/microsoft/PowerToys/wiki/Keyboard-Manager-Overview)
within a larger add-on software suite called [Power
Toys](https://github.com/microsoft/PowerToys/) (so you still have to
install something, but at least it's not third-party
software). Unfortunately, if you're working within the Windows
Subsystem for Linux (WSL) --- which gives you a Linux installation and
command line within Windows --- any Power Toys settings apparently do
not take hold (at least as of August 2020, [according to
emacswiki](https://www.emacswiki.org/emacs/MovingTheCtrlKey#toc26).

Emacswiki
[recommends](https://www.emacswiki.org/emacs/MovingTheCtrlKey#toc15)
installing an add-on (authored by Microsoft) called
["Ctrl2cap"](https://docs.microsoft.com/en-us/sysinternals/downloads/ctrl2cap)
that will intercept presses of `Caps Lock` and re-interpret them as
left `Ctrl`.  This isn't a full swapping -- left `Ctrl` will still be
control, so you lose the `Caps Lock` functionality altogether -- but
at least it achieves the important half of the swap.

The third-party [AutoHotKey
script](https://www.emacswiki.org/emacs/MovingTheCtrlKey#toc17) may
provide the best balance (but I haven't tested it myself).

Ultimately, direct editing of the Windows Registry may be the most
effective techinque. It requires Administrator privileges (which you
probably have on your own laptop) and then works systemwide (and is
easily reversed if you record what the earlier registry settings were
before you change them).  The process is described both on
[emacswiki](https://www.emacswiki.org/emacs/MovingTheCtrlKey#toc19)
and in this [reddit
post](https://www.reddit.com/r/bashonubuntuonwindows/comments/7exorl/remapping_caps_lock_key_in_linux_subsystem/).


## Helpful hints

* Up/down arrow let you navigate through your recent command history
  quickly.
  
* The `TAB` key can provide helpful autocompletion -- it matches *file
  and folder names* incrementally (one TAB will autocomplete if unique
  and pause if not unique; a 2nd TAB will show all possible
  completions to that point)

* Other key-navigation shortcuts that we can't focus on today but
  which help actualize your will on the command line with less
  latency.  Some examples (`M` denotes "meta" or "Alt" key -- Mac
  users need to enable "option as meta" in Terminal --> Preferences
  --> Keyboard (I think?) )
  
  ```
  C-a                     # Move cursor to start of line
  C-e                     # Move cursor to end of line
  C-d                     # Delete forward one character
  M-d                     # Delete forward one "word"
  M-backspace             # Delete backward one "word"
  M-f                     # Move cursor forward one "word"
  M-b                     # Move cursor backward one "word"

  C-t                     # Transpose char at cursor & previous one
  M-t                     # Transpose word at cursor & previous one

  M-u                     # Upper-case from cursor to end of word
  M-l                     # Lower-case from cursor to end of word
  M-c                     # Capitalize from cursor to end of word

  C-u                     # Delete from cursor to start of line
  C-k                     # Delete from cursor to end of line
  C-y                     # "Yank" (pasted) last thing deleted
  
  C-_                     # Undo your last editing command
  C-/                     # Undo your last editing command
  
  !!_                     # Last command in your history
  !$_                     # Last *argument* of last command
  ```

* `C-r`: reverse incremental search through history


## The importance of practice... and of playing "golf"

The only way to get better at the command line (or any skill) is to
use it *regularly*.  Challenge yourself to do more mouse-free.

### **ABG!**  (**A**lways **B**e **G**olfing!)

Also challenge yourself to do things in as few key-presses as possible
(like fewer strokes in golf). The command line can become quite
onerous if you have to type too much.  Train your fingers to make the
computer type as much as possible for you.

We willl start incorporating some "golfing" practice into the rest of
the workshop.
