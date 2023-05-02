---
title: Hardware
nav: true
---

# Use of Hardware
We make a distinction between the lab server, kennicott, which is a powerful computer in the basement of McClure, to which everyone in the group can log in, and also local computers, which might be a desktop or laptop.

An important concept is that different computers, like kennicott, can be operated from a different computer.    The address of kennicott, which is accessible while on the University of Idaho campus, is `kennicott.ibest.uidaho.edu`.  If you are off campus, you can make your computer *appear* to be on campus by using UI's vpn service.  Click [here to request vpn access from UI's ITS](https://support.uidaho.edu/TDClient/40/Portal/Requests/ServiceDet?ID=599).

kennicott can be accessed via a terminal and ssh or as a remote desktop, in which case you can operate kennicott and use kennicott's fast processors, graphics card, and large amount of RAM.  Alternatively, you can mount the kennicott hard drives as a local drive, in which case you can use kennicott's large amount of data storage and its data backups, but any computing happens on your local desktop or laptop computer, using your personal computer's processors and memory.


## Options for interacting with kennicott include the following:  
All require that you be on the university campus, or be using the UIdaho vpn (to appear as though you're on campus).

### Operating as a remote desktop (vnc):
This is likely the most straight-forward, most capable option, and the recommended one if you're just getting started.

This option uses a web browser to emulate the desktop/gui environment of the linux operating system that runs on kennicott.  You can then use a mouse to explore the file system, or open the terminal and interact with the file system through the command line.
1. In a web browser, navigate to [https://kennicott.ibest.uidaho.edu/vnc](https://kennicott.ibest.uidaho.edu/vnc)
2. Click "Connect" in the center of the page. 
3. From the dropdown menu, choose "Other..."
4. In the next box, enter your username without the @kennicott... suffix (for example, Chris Miele would enter `cmiele`).
5. Enter your password and hit "Log in." 

This will take you to a desktop-style interface with Kennicott. By clicking the black square icon at the bottom ("Terminal Emulator"), you can now access Kennicott through the command line. 

### Virtual Studio Code (vscode):
Virtual Studio Code is a popular program used for writing and testing different kinds of computer code.  Properly, it can be referred to as an Integrated Development Environment (IDE).  [VS Code](https://code.visualstudio.com/) is free software, offered by Microsoft, that can be run on any operating system.  Functionality within VS Code, for ssh, jupyter notebooks, etc. is added through "Extensions," many of which come with a blue check mark to indicate that they are official Microsoft version.  VS Code also offers native integration with git repositories, which make it convenient for working on collaborative projects.

If you install VS Code on your local computer/laptop, and then add the "Remote - SSH" extension from Microsoft, you can log into kennicott and work directly on files on this remote server.

### Logging in with a secure shell (ssh):
This option doesn't handle graphics nearly as well if you're not physically on campus.  However, it involves fewer overhead processes and may be preferable if you have a limited bandwidth connection and only need to operate kennicott textually, with the terminal.

* From a Windows machine, you'll want to use [PuTTY](https://www.chiark.greenend.org.uk/~sgtatham/putty/latest.html) (download and install the latest 64-bit MSI).  You'll also want to install and have running [XMing](https://sourceforge.net/projects/xming/).  Some instructions for navigating kennicott are given at the bottom of the '[Files](https://tbartholomaus.github.io/uiglaciology/2-files/)' page.
* From a Mac or Linux computer, open a terminal window (using either terminal or iTerm applications).  Then ssh into kennicott by typing `ssh -Y USERNAME@kennicott.ibest.uidaho.edu`, where `USERNAME` is your kennicott username.  Then enter your password.  Some instructions for navigating kennicott are given at the bottom of the '[Files](https://tbartholomaus.github.io/uiglaciology/2-files/)' page.  From a local mac or linux computer, files can be copied to a different computer that requires an ssh log-in (like kennicott) using [`rsync`](https://www.google.com/search?q=rsync+examples) (`scp` also works, but `rsync` has additional functionality that makes it more desirable for most uses).  A typical example might be:
   ```
   rsync -avzh PATH/TO/WHAT/TO/COPY USERNAME@kennicott.ibest.uidaho.edu:PATH/WHERE/FILE/OR/DIRECTORY/SHOULD/BE/COPIED/
   ```
   Some [attention is necessary regarding the use of slashes](http://qdosmsq.dunbar-it.co.uk/blog/2013/02/rsync-to-slash-or-not-to-slash/) at the end of the source (`WHAT/TO/COPY`) path, when using `rsync`. A slash at the end means copy the directory's contents.  No slash means copy the directory, as well as its contents.

### Mounting /data/stor as a local drive:
This option allows you to use files stored on kennicott, and then manipulate them on your local computer.  Any processing of the files happens with your local computer's processors and memory.

On a Windows, Mac, or Linux computer, kennicott can be mounted via samba to the local computer filesystem.  Then, files can be transferred to and from kennicott's directories as though it were a local hard drive. 

### Transfering files using sftp and 3rd party applications:
On a Windows, Mac, or Linux computer, you can manipulate files (copying/moving/renaming/deleting) via some 3rd party applications that use sftp, such as [Filezilla](https://filezilla-project.org/) on a Windows computer or [cyberduck](https://cyberduck.io/) on a Mac.

Talk to Tim about any of the options, or for more information.





## Coding in Kennicott

To access a Python interface (an Integrated Development Environment, IDE) like Spyder or Jupyter Lab, first specify a conda environment. It may be useful to [clone one of Kennicott's existing environments](https://conda.io/projects/conda/en/latest/user-guide/tasks/manage-environments.html#cloning-an-environment) and work from that cloned environment. This way, you're free to modify (or even break) your own cloned environment without impacting anyone else. For example, rather than using the environment "spatialenv21b," Chris Miele created a clone of this environment, named "chrisenv." Now each time he logs onto Kennicott, he types `source activate chrisenv` to activate this environment. Typing `spyder` then opens a Spyder interface, from which you can write, run, and save scripts. 



## Where to do your computing
We do most computing on the group server, kennicott, where we can access each other's scripts and access shared, group datasets.  See  the '[Files](https://tbartholomaus.github.io/uiglaciology/2-files/)' page on this site for more information and suggestions about how to organize your work.

