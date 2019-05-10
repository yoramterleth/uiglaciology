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


### basic_data
basic_data is where unmodified, broadly useful data, are stored.  Filenames shouldn't be renamed- they should be retained as downloaded or received.  Metadata should be stored with the data.

### proj
proj is for individual projects that each of us are working on.  This is where any derived data or analysed data should go.

### Home directory
Tim recommends against using this directory for most purposes.  It is not accessible to others under most circumstances.  It's better to work on projects in a transparent, centralized, and accessible way.

## On your local computer
Don't do significant computing on your local computer if it's not being backed up on OneDrive.  Whenever possible, do your work on kennicott.

---

# Navigating the file system
On linux, which is the operating system running on kennicott, there are a few commands that will be useful in navigating the file system.  Each of these have flags, which are run with a hyphen and then some additional character, for instance `-h` to make the output into human readable file sizes.  Type `man ls`, for instance, to see the manual page, and the definition of any flags and how to use a command in linux.

These useful commands, with some common flags include:
```
pwd
cd
ls -l -h
ls | head -20  # for listing enclosed files, piping the output to head, and then showing just the first 20 files in the directory
du -h -d 2     # for identifying the amount of disk space in directories
tree -L 2      # for creating a graphical output of a directory structure
```


# OLD Below


{% include figure.html img="color-color-paper-colored-paper-268347.jpg" alt="sticky notes by rawpixels.com" %}

## Instructor Prep

- [Instructor Training materials](https://carpentries.github.io/instructor-training/), community discussions, mentoring groups
- Practice with video!
- Have clear install / setup solutions
    - bring USB with required downloads
    - include instructions for all OS and emergency alternatives
    - learn from others about common problems 
- Session leader + helpers

## Environment 

Establish a safe space for learning 

- [Code of Conduct](https://docs.carpentries.org/topic_folders/policies/code-of-conduct.html) - foster a welcoming, supportive environment to learn (and fail)
- Peer teachers create a more comfortable learning environment
    - instructors and helpers are often peer researchers, and are learners as well
    - participants pair up on exercises, encourage helping each other
    - pair programming
- Prep your vocabulary
    - Avoid "easy" and "just" - recognize barriers and demystify, sensitive to impostor syndrome
    - Avoid "dismissive language" of experts - don't demean certain applications, OS, etc. 
    - "What questions do people have?"
    - Acknowledge confusion
    - Demotivating
- Understand learner motivations
    - Not CS. Teach what is useful!


## Sticky Notes

Participants receive red and green sticky notes used for communicating feedback during the sessions. 

- Red sticky note = non-intrusive, discreet means to get help
- *Once you get to X put up your Green sticky...*
- Instant assessment questions
    - identify misconceptions
- "Minute Cards"
    - Continuous feedback built in to the end of each session 
    - Write down one positive, one negative, remaining questions
    - instructors review during breaks and address = responsive to learners. Be explicit so learners know you are listening!

## Participatory Live Coding

- BYO Device - participants are most comfortable with their own machine, plus need to get it set up correctly for further research and learning.
- Real data - walk through concrete examples with realistic scenarios rather than abstract concepts. "media computing"
- Live Coding + Code-along
    - Continuous practice-feedback loop - teach from mistakes, the art of troubleshooting 
    - Speak out loud about everything you are doing! 
    - Model behavior, e.g. common shortcuts 
    - Go Slow! Help participants build "mental models" of how coding works, not cram them full of information.
    - Prep your machine: big fonts, accessible colors, notifications off, non-customized look
- Collaborative note taking 
    - Etherpad, Google Doc
    - Peer support, chat
    - links, resources, quiz answers
    - keep accessible after the session
- Reduce cognitive load 
    - Minimize window / app switching! 
    - Structure lessons to introduce only a handful of concepts at a time (use concept mapping to figure out how many things you are actually trying to introduce!)
    - Guided practice

## Assessment 

- Pre + post surveys for each workshop
- [long term impact survey](https://docs.carpentries.org/topic_folders/assessment/assessment.html)
- Research
- Evidence based practice 
