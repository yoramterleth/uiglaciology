---
title: Code
nav: true
---

# Working with python
Google is your friend for learning how to code.  Tim also recommends [scipy-lectures.org](https://scipy-lectures.org/) as a good consistent primer on a lot of fundamental coding tasks. The [python website](https://wiki.python.org/moin/BeginnersGuide) also provides useful tutorials that are helpful for beginners.

Stack Overflow and Stackexchange are invaluable tools for professional, beginner, and enthusiastic programmers. Both are question and answer platforms used across the programming community to solve coding problems collaboratively.	 They will frequently come up in Google searches.

We generally use python for most of our core scientific computing needs.  We use anaconda as a package manager for installing and updating python, spyder, and necessary packages such as numpy, scipy, etc...  You can [learn more about managing and installing packages here](https://docs.conda.io/projects/conda/en/latest/user-guide/tasks/manage-pkgs.html#).

## Environments: internally consistent sets of python modules
If you want to use python on kennicott, after you log in, type `conda activate`.  You might want to append this to the end of your `~/.bashrc` file, which is a text file that runs automatically every time you log into kennicott. Different sets of packages for different purposes are organized into specific "environments," which are kept internally consistent.  You can identify the available environments by typing `conda env list`.  In spring 2019, there are four main environments that are available to all users on kennicott: base (fundamental, basic scientific computing packages), seisenv_yml (for the purpose of working with obspy and seismic data), spatialenv_yml (for the purpose of working with spatial data, like shapefiles, geotiffs, and other rasters), and imgenv_yml (for image processing with opencv, PIL, etc.).  Each of these environments is maintained [on github as well, here,](https://github.com/tbartholomaus/conda_envs) so you can suggest changes, or download them yourself to have consistent environments on personal and work computers. You can change to one of these environments by typing `conda activate myenv`, in which case you replace `myenv` with the name of the environment you want to use. If there are python modules you'd like to use that don't fall in one of these categories, you can [create your own environment](https://docs.conda.io/projects/conda/en/latest/user-guide/tasks/manage-environments.html#creating-an-environment-with-commands), or [clone an existing environment](https://docs.conda.io/projects/conda/en/latest/user-guide/tasks/manage-environments.html#cloning-an-environment) and then modify it for your purposes.

## Preferred python interface
Our lab generally uses the spyder integrated development environment for writing, running, debugging, and plotting tasks with python.  You can open this program by typing `spyder` at the terminal window.



## Helpful native Python functions
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

## Helpful Python Modules
1. os module
- `os.listdir(directory_path)`
- `os.path.join(path_stem, filename)`

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
   which will allow the `my_py_script.py` to run on kennicott and prevent the server from killing the process if the server becomes disconnected.  The `-u` flag forces the text output of the python script to stdout (i.e., 'standard out', which is typically to a computer monitor), so that it can then be redirected (with `>`) to a log file (`File_to_collect_output.log`).  Ending the line with an `&` moves the running command (aka, 'a process') into the background, so that the terminal window can still be controlled.

3) When you begin a command in the background, with `&`, at the terminal just below your command, you'll see a 4 to 6 digit number.  This number is the PID number, and is the number that the computer uses to track and identify the process you just launched.  If you're moving commands/processes into the background, you should be aware that some of these processes can become forgotten, zombie processes, that tie up computer resources and never actually quit or finishe running.  If you start using nohup, it's your responsibility to keep an eye on the system resources you're using.  You can view all the processes you're responsible for by typing at the linux terminal: `ps -x`.  This will show a list of processes attributed to you, their PID numbers, and the commands that generated these processes.  To terminate a process and free up computer resources, use the command `kill`.  For example, to end processes 2502 and 2507, type `kill 2502 2507`.  `top` is another useful command that dynamically updates to show you all the processes that are running, who owns them, and what computer resources they're consuming.  Another way to use ps is `ps -eo pid,etime,comm`, that puts some focus on the elapsed time of each process.

# Geographic information systems (GIS)
[QGIS](https://www.qgis.org/en/site/) is a great tool for working with spatial data, like rasters and shapefiles.  It's free and has a lot of capability.
