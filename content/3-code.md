---
title: Code
nav: true
---


# Python
<br/>

## How to get started on your personal computer with python, Anaconda, and environments
Here are four steps you can follow to start working with python:
1. _Download and install the [Anaconda individual edition](https://docs.anaconda.com/anaconda/install/)_<br/><br/>
  Anaconda/conda both installs python and creates a system by which you can expand python's functionality through "packages" or "modules." You can [learn more about managing and installing packages here](https://docs.conda.io/projects/conda/en/latest/user-guide/tasks/manage-pkgs.html#).<br/>
  If you're given the option, you'll likely want a 64 bit version (as compared to a 32 bit version). If given the option, use python 3, not python 2. python 2 is obsolete. Tim doesn't have any experience with PyCharm, and so hasn't chosen to install it himself.<br/>
  **Before you proceed,** review the [Getting Started with Conda website](https://docs.conda.io/projects/conda/en/latest/user-guide/getting-started.html).<br/>
  

2. _Set up your conda environments_<br/><br/>
  This step is technically optional, but recommended before you dive into new projects.  It is necessary if you plan to work with Jupyter Hub.<br/>
  Scientific computing with python is done using "packages" or "modules."  Some combinations of modules might be incompatible.  Anaconda helps maintain mutually consistent modules, but environments take this a step further.  By creating separate "environments," you create different virtual _workshops_ or _sandboxes_ in which all the tools are designed to work well together, and not conflict.<br/>
  Some of the environments that the UI Glacier Dynamics Lab (and Tim personally) uses for his projects are hosted on github [here](https://github.com/tbartholomaus/conda_envs).<br/>
  You can also [learn more about conda environments below](https://github.com/tbartholomaus/uiglaciology/blob/master/content/3-code.md#environments-internally-consistent-sets-of-python-modules).<br/>

3. _Start coding_<br/><br/>
  Open either Spyder or Jupyter Lab to start a user-friendly interface for interacting with and coding python, and coding. <br/><br/>

4. _Learning python_<br/><br/>
  If you are new to python, or just need a consistent primer for what's involved in python's core functionality, Tim recommends starting with [scipy-lectures.org](https://scipy-lectures.org/).  You can use the website itself or download the entire lecture set as a 600+ page PDF and scroll through it (Tim's preferred method).  To start, read and work through Chap 1 ("Python scientific computing ecosystem"), Chap 2 ("The Python language" sections "First Steps," "Basic types," and "Control Flow"), and then all of Chap 4 ("NumPy") and Chap 5 ("Matplotlib"). <br/>
  The [python website](https://wiki.python.org/moin/BeginnersGuide) also provides useful tutorials that are helpful for beginners. <br/>
  Once you are past the basics, googling for answers is essential.  Stack Overflow and Stackexchange are invaluable tools for professional, beginner, and enthusiastic programmers. Both are question and answer platforms used across the programming community to solve coding problems collaboratively.	 They will frequently come up in Google searches.<br/>


## Environments: internally consistent sets of python modules
If you want to use python on kennicott, after you log in, type `conda activate`.  You might want to append this to the end of your `~/.bashrc` file, which is a text file that runs automatically every time you log into kennicott. Different sets of packages for different purposes are organized into specific "environments," which are kept internally consistent.  You can identify the available environments by typing `conda env list`.  In spring 2019, there are four main environments that are available to all users on kennicott: base (fundamental, basic scientific computing packages), seisenv_yml (for the purpose of working with obspy and seismic data), spatialenv_yml (for the purpose of working with spatial data, like shapefiles, geotiffs, and other rasters), and imgenv_yml (for image processing with opencv, PIL, etc.).  Each of these environments is maintained [on github as well, here,](https://github.com/tbartholomaus/conda_envs) so you can suggest changes, or download them yourself to have consistent environments on personal and work computers. You can change to one of these environments by typing `conda activate myenv`, in which case you replace `myenv` with the name of the environment you want to use. If there are python modules you'd like to use that don't fall in one of these categories, you can [create your own environment](https://docs.conda.io/projects/conda/en/latest/user-guide/tasks/manage-environments.html#creating-an-environment-with-commands), or [clone an existing environment](https://docs.conda.io/projects/conda/en/latest/user-guide/tasks/manage-environments.html#cloning-an-environment) and then modify it for your purposes.

## Preferred python interface
Our lab uses two different programs or front-ends for interacting with python, and writing, running, debugging, and plotting tasks.

These two approaches are:

|**Spyder**|**Jupyter Lab**|
| :-: | :-: |
| You can open this program by typing `spyder` at the terminal or Anaconda Prompt window. | Jupyter Lab runs in a web browser window and you can open it by typing `jupyter lab` at the terminal or Anaconda Prompt.|
| Spyder is generally a little better for complete scripting, and writing out more complicated computing workflows. Spyder is very similar to the Matlab user interface. | Jupyter Lab is potentially more useful for data exploration, and it allows text and figures to be stored right with the code.|
| ![Spyder screenshot](../images/spyder.png) | ![Jupyter screenshot](../images/jupyter.png =230x) |


 =250x



## Helpful native Python functions

<details>
<summary>Click for dropdown</summary>

1. Loop Functions: useful when using `for` loops
- `zip`

  zip function zips two lists of the same length together so that you can iterate through both at the same time.  This function is especially handy when plotting multiple subplots in one loop where you want to specify different axes labels, xticks, etc as you can zip these together and just iterate through once.
  
  Example:

  ```
  numbers = [1,2,3,4,5]
  letters = ['a','b','c','d','e']
  for number,letter in zip(numbers, letters):
    print(number, letter)
  ```
    
  Output:
   ```
   1 a
   2 b    
   3 c
   4 d
   5 e
   ```

- `enumerate`

  The enumerate function is superbly useful as it returns both the index number of elements in a list and the element values themselves in one line. 
  
  As an example:
  
  ```
  letters = ['a','b','c','d','e']
  for index, letter in enumerate(letters):
    print(index, letter)
   ```
    
   Output:
    ```
      0 a
      1 b
      2 c
      3 d
      4 e
    ```

 
  
2. Managing data types
- `list((data))`
- `np.array((data, dtype=int))`
- `np.array((data, dtype=np.float64))`


</details>
<br/>


## Keeping a script running overnight (or other long periods)
You might try and take advantage of kennicott's resources to run a script overnight, or for some other long period of time, then have the script write the output to some other kind of file, like text, csv, pickle, or npz.  If logged into kennicott via ssh, sometimes, if the connection isn't "active" in some way, you'll get booted off of kennicott.  And when you get booted off kennicott, the process (aka, application or script) that you're running and controlling via the ssh connection will be "killed" when you apparently "hang up" the connection on kennicott.  In that case, any work stored in memory is lost.

To get around the problem of hanging up on a process, 1) run the script directly from the terminal (rather than spyder), and 2) [use the `nohup` bash command](https://linux.101hacks.com/unix/nohup-command/) within the linux terminal window, to keep the script running in case of hangup, and 3) keep a close eye on the processes that you're running.  One example of this is a script Tim wrote to process seismic data.  See the [github README.md file](https://github.com/tbartholomaus/med_spec) for more information on this application, and the referenced python scripts for examples of how this works.  

1) To execute a script from the terminal, rather than within spyder, you'll have to [let the computer know how to read the script](https://stackoverflow.com/questions/27494758/how-do-i-make-a-python-script-executable) by adding specific header information to the top of the script you want to run, such as 
   ```
   #!/opt/anaconda/envs/seisenv/bin python
   # -*- coding: utf-8 -*-
   ```
   In the above, case, the first line, known as a "shebang" indicates what specific conda environment the script should be run from.

2) An example of using nohup is
   ```
   nohup python -u ./my_py_script.py > File_to_collect_output.log &  
   ```
   which will allow the `my_py_script.py` to run on kennicott and prevent the server from killing the process if the server becomes disconnected.  The `-u` flag forces the text output of the python script to stdout (i.e., 'standard out', which is typically to a computer monitor), so that it can then be redirected (with `>`) to a plain text log file (`File_to_collect_output.log` -- the `log` extension is arbitrary, and could be anything).  Ending the line with an `&` moves the running command (aka, 'a process') into the background, so that the terminal window can still be controlled.

3) When you begin a command in the background, with `&`, at the terminal just below your command, you'll see a 4 to 6 digit number.  This number is the PID number, and is the number that the computer uses to track and identify the process you just launched.  If you're moving commands/processes into the background, you should be aware that some of these processes can become forgotten, zombie processes, that tie up computer resources and never actually quit or finishe running.  If you start using nohup, it's your responsibility to keep an eye on the system resources you're using.  You can view all the processes you're responsible for by typing at the linux terminal: `ps -x`.  This will show a list of processes attributed to you, their PID numbers, and the commands that generated these processes.  To terminate a process and free up computer resources, use the command `kill`.  For example, to end processes 2502 and 2507, type `kill 2502 2507`.  `top` is another useful command that dynamically updates to show you all the processes that are running, who owns them, and what computer resources they're consuming.  Another way to use ps is `ps -eo pid,etime,comm`, that puts some focus on the elapsed time of each process.

# Geographic information systems (GIS)
[QGIS](https://www.qgis.org/en/site/) is a great tool for working with spatial data, like rasters and shapefiles.  It's free and has a lot of capability.
