---
title: Hardware
nav: true
---

# Use of Hardware
We make a distinction between the lab server, kennicott, which is a powerful computer in the basement of McClure, to which everyone in the group can log in, and also local computers, which might be a desktop or laptop.

An important concept is that different computers, like kennicott, can be operated from a different computer.    The address of kennicott, which is accessible while on the University of Idaho campus, is `kennicott.ibest.uidaho.edu`.  If you are off campus, you can make your computer *appear* to be on campus by using UI's vpn service.  Click [here to request vpn access from UI's ITS](https://support.uidaho.edu/TDClient/40/Portal/Requests/ServiceDet?ID=599).

kennicott can be accessed via a terminal and ssh, in which case you can operate kennicott and use kennicotts fast processors and large amount of RAM.  Alternatively, you can mount the kennicott hard drives as a local drive, in which case you can use kennicott's large amount of data storage and its data backups, but any computing happens on your local desktop or laptop computer, using your personal computer's processors and memory.

Options for interacting with kennicott include the following.  All require that you be on the university campus, or be using UI vpn.
* From a Windows machine, you'll want to use [PuTTY](https://www.chiark.greenend.org.uk/~sgtatham/putty/latest.html) (download and install the latest 64-bit MSI).  You'll also want to install and have running [XMing](https://sourceforge.net/projects/xming/).  Some instructions for navigating kennicott are given at the bottom of the ['Files'](https://tbartholomaus.github.io/uiglaciology/2-files/) page.
* From a Mac or Linux computer, open a terminal window (using either terminal or iTerm applications).  Then ssh into kennicott by typing `ssh -Y USERNAME@kennicott.ibest.uidaho.edu`, where `USERNAME` is your kennicott username.  Then enter your password.  Some instructions for navigating kennicott are given at the bottom of the ['Files'](https://tbartholomaus.github.io/uiglaciology/2-files/) page.  From a local mac or linux computer, files can be copied to a different computer that requires an ssh log-in (like kennicott) using [`rsync`](https://www.google.com/search?q=rsync+examples) (`scp` also works, but `rsync` has additional functionality that makes it more desirable for most uses).  A typical example might be:
```
rsync -avzh PATH/TO/WHAT/TO/COPY USERNAME@kennicott.ibest.uidaho.edu:PATH/WHERE/FILE/OR/DIRECTORY/SHOULD/BE/COPIED/
```
Some [attention is necessary regarding the use of slashes](http://qdosmsq.dunbar-it.co.uk/blog/2013/02/rsync-to-slash-or-not-to-slash/) at the end of the source (`WHAT/TO/COPY`) path. A slash at the end means copy the directory's contents.  No slash means copy the directory, as well as its contents.
* On a Windows, Mac, or Linux computer, kennicott can be mounted via samba to the local computer filesystem.  Then, files can be transferred to and from kennicott's directories as though it were a local hard drive. 
* On a Windows, Mac, or Linux computer, you can manipulate files (copying/moving/renaming/deleting) via some 3rd party applications that use sftp, such as [Filezilla](https://filezilla-project.org/) on a Windows computer or [cyberduck](https://cyberduck.io/) on a Mac.

Talk to Tim about any of the options, or for more information.

We do most computing on the group server kennicott where we can access each other's scripts and access group datasets.  See  the ['Files'](https://tbartholomaus.github.io/uiglaciology/2-files/) page on this site for more information and suggestions about how to organize your work.

