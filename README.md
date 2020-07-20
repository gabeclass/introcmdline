# Intro to the Linux Command Line

## This presentation

[https://github.com/gabeclass/introcmdline](https://github.com/gabeclass/introcmdline)

## About
These are reference materials for the PiCSciE _virtual_ workshop
**Intro to the Linux Command Line** at Princeton. Most of this
material is covered interactively and adapted as much as possible to
the audience at any given workshop.

<!--- At the start of the workshop, participants will see how to
capture every command they type, along with the output and any notes
and comments -- **everyone will have a personalized record of what
happens in the session.** Consequently, very little is posted on this
page. -->

This workshop does not assume prior experience with Linux/Unix systems
or the bash shell, nor does it assume that you have previously worked
with a command-line interface (CLI) to a computer.

## Adroit
The workshop *does* assume that you have an account on the Adroit
cluster (a shared Linux cluster at Princeton on which we will do our
work during the workshop) *and* that you can access Adroit via
SSH. The PICSciE website offers
[instructions](https://researchcomputing.princeton.edu/education/training/virtual-workshop-requirements)
for how to connect via SSH.

NOTE that connecting to Adroit (or to the web interface MyAdroit
described below) requires that you be on the Princeton **eduroam**
network if connecting from on-campus (the **puvisitor** network will
*not* allow a connection to Adroit) or on a [Princeton
VPN](https://princeton.service-now.com/snap?id=kb_article&sys_id=ce2a27064f9ca20018ddd48e5210c745)
(if connecting from off-campus) or .  In either case (on- or
off-campus), you must be able to Duo authenticate when prompted.

### MyAdroit web interface
Adroit also offers a web interface called
[**MyAdroit**](https://myadroit.princeton.edu/) that provides a
command-line shell plus a graphical file browser. However, **_MyAdroit
is not recommended for this workshop_**, since some of the keyboard
shortcuts we will be using do not work via the web interface.  Please
use MyAdroit only if you have no other way to connect to the Adroit
cluster.

<!--If MyAdroit is your only alternative for connecting to Adroityou
must be on the Princeton **eduroam** network (the **puvisitor**
network will *not* allow a connection to Adroit), and you must be able
to Duo authenticate. If you were off campus, you would be establish a
connection to Princeton's VPN first.  OIT has
[instructions](https://princeton.service-now.com/snap?id=kb_article&sys_id=ce2a27064f9ca20018ddd48e5210c745)
for how to do that.

When you're ready, please log in to myadroit
[here](https://myadroit.princeton.edu/). -->

<!-- You can find the page, presentation and examples either in the
[src/](src/) folder or hosted via Github Pages at
[https://princetonuniversity.github.io/hpc_beginning_workshop/](https://princetonuniversity.github.io/hpc_beginning_workshop/)
-->

## **WARNINGS!**


* **Linux is _case-sensitive_** (Windows and macOS, in contrast, are
  usually case-*insensitive*, depending on how your hard drive's
  filesystem was configured).

* **The command-line is _unforgiving_!** Type things *EXACTLY* as you
  see them, and avoid interpreting (and don't assume the computer will
  interpret anything for you -- be precise).


## For one of our exercises

Here is a plain text (ASCII) version of the [US Declaration of
Independence](https://web.math.princeton.edu/~perezgiz/usdec.txt)
(from Project Gutenberg).


<!---
This version still has CRLF returns and lots of header and footer information
https://ia800305.us.archive.org/29/items/unitedstatesdecl00001gut/when12.txt
-->

<!---
[https://www.constitution.org/usdeclar.txt](https://www.constitution.org/usdeclar.txt)
-->

## Instructions for setting up SSH keys (passwordless SSH)

[Set up SSH keys](https://www.digitalocean.com/community/tutorials/how-to-set-up-ssh-keys-on-ubuntu-1604)

<!---
## Google Survey
Near the end of the workshop, you'll be asked to fill out a brief (3-5
mins) survey. When the time comes, please
[click here](https://forms.gle/WhoAcb1J82XVTqq38).
-->

## Resources for further study

* _The Linux Command Line_ (a book by William Shotts -- [free PDF
online](http://linuxcommand.org/tlcl.php)

* _Introduction to Linux: A Hands on Guide_ (a book by Machtelt
  Garrels -- free PDFs discoverable online; [full HTML
  version](https://www.tldp.org/LDP/intro-linux/html/) is online)
  

<!---
* Afternoon session (Intro to HPC on the Princeton Clusters)

* Wednesday session (Command Line Power Tools -- moves faster, a bit
  more advanced, but worth seeing even if you can't keep up this time
  around)
-->

<!-- [Getting Started with
HPC at
Princeton](https://researchcomputing.princeton.edu/education/online-tutorials/getting-started)
--> <!-- [OnComputingWell](https://oncomputingwell.princeton.edu) -->
<!-- [Research Computing
FAQ](https://researchcomputing.princeton.edu/faq) --> <!--
[AskRC](https://researchcomputing.princeton.edu/about/contact/ask-research-computing)
-->

## Getting Help Later

If you encounter difficulties working on the PU computing systems or
have basic Linux questions, please drop in to one of PICSciE's twice
weekly <a
href="https://researchcomputing.princeton.edu/education/help-sessions">live
help sessions</a>, visit our blog
[*OnComputingWell*](https://oncomputingwell.princeton.edu) to see if
someone has answered your question, post your question on our Q&A site
[AskRC](https://researchcomputing.princeton.edu/about/contact/ask-research-computing),
or send an email to <a
href="mailto:cses@princeton.edu">cses@princeton.edu</a>.

<!--
## About Makefile
I update the documentation directory using a Makefile to sync src/ and docs/, with
the 'Dinky' theme because its seemed apropros of Princeton. To run it, just run
`make` from the repo root.
-->

## Authorship

This workshop was prepared by Gabe Perez-Giz. It incorporates some
elements from an earlier incarnation of this workshop by Ben Hicks and
borrows some pieces from Jonathan Halverson.
