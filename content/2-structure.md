---
title: Structure
nav: true
---

# File Structure and Organization

Use OneDrive to back up your work, and keep it synchronized between different computers.  OneDrive is Microsoft's answer to Dropbox, or Google Drive.  Grad students get a significant amount of free storage (___ Gb)- don't hesitate to make the most of it.

## On kennicott

There are three fundamental directories on kennicott:
- basic_data
    - at `/data/stor/basic_data/`
- proj
    - at `/data/stor/proj/`
- The home directory
    - at `~` or `/home/user_name`, in which `user_name` is your user name, for logging into kennicott, for example your first initial and last name, run together without spaces.
    
 #TEST SWAN_PULL

### basic_data
basic_data is where unmodified, broadly useful data, are stored.  Filenames shouldn't be renamed- they should be retained as downloaded or received.  Metadata should be stored with the data.

When possible, simple, minimalist scripts that access and perhaps plot these data can and should be stored here as well, with sufficient commenting in the script header.  Minimalist, generic scripts that are useful to others reduce the "startup costs" of working with the data.

### proj
proj is for individual projects that each of us are working on.  This is where any derived data or analysed data should go that contributes to a specific project, but is unlikely to be useful to others not working on the project..

### Home directory
Tim recommends against using this directory for most purposes.  It is not accessible to others under most circumstances.  It's better to work on projects in a transparent, centralized, and accessible way.

### Backups on kennicott
basic_data, proj, and your home directory are backed up annually on the first of the year, as well as monthly and daily.  Monthly snapshots of the data are retained for 6 months and daily snapshots of the data are retained for 8 days only.  As a result, changes and deletions to files in these locations can be undone/recovered if identified quickly enough, while a snapshot exists of the file system.  If you need files recovered, please contact Tim or [Benji Oswald](https://crc.ibest.uidaho.edu/contact.html) at the [CRC of IBEST](https://crc.ibest.uidaho.edu/index.html) as quickly as possible. Existing snapshots on kennicott can be identified by typing `zfs list -t snapshot` at the terminal.

Hard drives on kennicott are currently mirrored, to provide redundancy in the event of hard drive failure.  As of May 2019, Tim is also pursuing offsite storage, outside of McClure, as an additional source of data security and redundancy.

## On your local computer
Don't do significant computing on your local computer if it's not being backed up on OneDrive.  Whenever possible, do your work on kennicott.

---

# Navigating the file system
On linux, which is the operating system running on kennicott, there are a few commands that will be useful in navigating the file system.  Each of these have flags, which are run with a hyphen and then some additional character, for instance `-h` to make the output into human readable file sizes.  Type `man ls`, for instance, to see the manual page, and the definition of any flags and how to use a command in linux.

These useful commands, with some common flags include:
```
pwd            # show the present working directory
cd             # change the directory
ls -l -h       # list the files enclosed within the present directory
ls | head -20  # for listing enclosed files, piping the output to head, 
               #    and then showing just the first 20 files in the directory
mv             # move or rename a file or directory
du -h -d 2     # for identifying the amount of disk space in directories
tree -L 2      # for creating a graphical output of a directory structure
```
