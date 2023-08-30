---
title: Files
nav: true
---

# File Structure and Organization
Most of your significant research efforts should take place on kennicott, or at least be saved there from time to time.  When you graduate or move on from the University, I'll ask that you store all your work products on kennicott, so that they are accessible in the future.

## On kennicott

kennicott is the name of the lab group server that we use for powerful computing and data storage.  There are three fundamental directories on kennicott:
- basic_data
    - at `/data/stor/basic_data/`
- proj
    - at `/data/stor/proj/`
- The home directory
    - at `~` or `/home/user_name`, in which `user_name` is your user name, for logging into kennicott, for example your first initial and last name, run together without spaces. However, please don't save files to your home directory (see below).


### basic_data
basic_data is where unmodified or lightly-modified, broadly useful data, are stored.  Filenames shouldn't be renamed- they should be retained as downloaded or received.  Metadata should be stored with the data.  Files within `basic_data` are most useful when they have a little "readme" file accompanying it that reports who downloaded or produced the data, when, from where, and why.

When possible, simple, minimalist scripts that access and perhaps plot these data can and should be stored here as well, with sufficient commenting in the script header.  Minimalist, generic scripts that are useful to others reduce the "startup costs" of working with the data.

Seismic data within `basic_data` should include raw data recovered from the field, day volumes, response or stationxml files, and any 1st- or 2nd-order products (like sensor orientation products).

### proj
proj is for individual projects that each of us are working on.  This is where any derived data or analysed data should go that contributes to a specific project, but is unlikely to be useful to others not working on the project.  Subdirectories of `proj` should have a name associated with a specific effort, at the scale aimed at potential publication.

Each of these specific efforts should then have additional subdirectories oriented around specific analyses that contribute to the effort, for instance, different data types, models, folders for scripts, folders for figures, etc.  An example of this heierarchical structure can be found in the directory `proj/Calv_Val`. Any scripts used to produce these analyses should be stored with the analysis output in a straightforward way, by which output can be intuitively linked back to the scripts that created them.

### Home directory
Your home directory is the default directory you'll arrive in when you first log into kennicott, and has the name of your kennicott username. However, please do not use this directory. You may download files here, but then please immediately delete them after you've moved them into an appropriate `basic_data` or `proj` directory.  There is very little disk space allocated to these home directories, nor are they accessible to others.  It's better to work on projects in a transparent, centralized, and accessible way, within `/data/stor/proj/`.

### Backups of kennicott
basic_data, proj, and your home directory are backed up annually on the first of the year, as well as monthly and daily.  These backups are stored locally, on kennicott itself.  Monthly snapshots of the data are retained for 6 months and daily snapshots of the data are retained for 8 days only.  As a result, changes and deletions to files in these locations can be undone/recovered if identified quickly enough, while a snapshot exists of the file system.  If you need files recovered, please contact Tim or [Benji Oswald](https://www.hpc.uidaho.edu/general/Staff/) at [Research Computing ad Data Services](https://crc.ibest.uidaho.edu/index.html) as quickly as possible. Existing snapshots on kennicott can be identified by typing `zfs list -t snapshot` at the terminal.

Hard drives on kennicott are mirrored, to provide redundancy in the event of a single hard drive failure.

Data from kennicott are also backed up off-site, in the event of a catastrophic loss of kennicott.  We use the cloud backup system IDrive.  This system stores recent backups of files every day, in the middle of the night.  IDrive saves current and older versions of all files in `/data/stor/`, including proj and basic_data, and maintains a backup of all files that have been deleted. Contact Tim if you would like help recovering any old files or old versions of files.

## Backups for your local computer
Please don't do significant computing on your local computer.  However, any products or classwork that you do work on, locally, can and should be [backed up on OneDrive](https://support.uidaho.edu/TDClient/40/Portal/Requests/ServiceDet?ID=864#:~:text=In%20addition%2C%C2%A0a%20person%C2%A0can%20sync%C2%A0OneDrive%C2%A0to%20a%20U%20of%20I%20owned%20computer%20so%20that%20frequently%20used%20are%20stored%20on%20a%20physical%20computer%C2%A0for%20easy%20access%20when%20you%20have%20limited%20or%20no%20Internet%20connection.), which is Microsoft's answer to cloud storage like Dropbox or Google Drive.  Every student, faculty, and staff get a significant amount of free storage (5 Tb) so make the most of it.  When you [install the OneDrive app](https://www.microsoft.com/en-us/microsoft-365/onedrive/download) (or use it natively on a Windows computer), then your OneDrive files are saved on your own personal computer and are available for your use, but they also will sync up to the OneDrive in the cloud, providing for a seemless, automatic backup of your files. You should configure your personal/work computer so that _every single piece of work_ that you do, for research, classes, and heck, even your personal files, are backed up continuously to the cloud via OneDrive. Ask Tim if you have any questions about how to do this.

The free access that we have to huge, cloud data volume storage on OneDrive is awesome, and we should all make abundant use of it.  But whenever possible, do your research work on kennicott so that it is available to all.

---

# Navigating the file system
On linux, which is the type of operating system running on kennicott, there are a few commands that will be useful in navigating the file system.  Each of these have flags, which are run with a hyphen and then some additional character, for instance `-h` to make the output into human readable file sizes.  Type `man ls`, for instance, to see the manual page, and the definition of any flags and how to use a command in linux.

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
