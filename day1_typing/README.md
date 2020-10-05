# Typing more easily in the shell

## Swap Caps Lock and left Ctrl

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
