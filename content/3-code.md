---
title: Code
nav: true
---

# Working with python
Google is your friend for learning how to code.  Tim also recommends [scipy-lectures.org](https://scipy-lectures.org/) as a good consistent primer on a lot of fundamental coding tasks. The [python website](https://wiki.python.org/moin/BeginnersGuide) also provides useful tutorials that are helpful for beginners.

Stack Overflow and Stackexchange are invaluable tools for professional, beginner, and enthusiastic programmers. It is a question and answer platform used across the programming community to solve coding problems collaboratively.	 It will frequently come up in Google searches.

We generally use python for most of our core scientific computing needs.  We use anaconda as a package manager for installing and updating python, spyder, and necessary packages such as numpy, scipy, etc...  You can [learn more about managing and installing packages here](https://docs.conda.io/projects/conda/en/latest/user-guide/tasks/manage-pkgs.html#).

If you want to use python on kennicott, after you log in, type `conda activate`.  You might want to append this to the end of your `~/.bashrc` file, which is a text file that runs automatically every time you log into kennicott. Different sets of packages for different purposes are organized into specific "environments," which are kept internally consistent.  You can identify the available environments by typing `conda env list`.  In spring 2019, there are three main environments that are available to all users on kennicott: base (fundamental, basic scientific computing packages), seisenv (for the purpose of working with obspy and seismic data), and spatialenv (for the purpose of working with spatial data, like shapefiles, geotiffs, and other rasters).  If there are python modules you'd like to use that don't fall in one of these categories, you can [create your own environment](https://docs.conda.io/projects/conda/en/latest/user-guide/tasks/manage-environments.html#creating-an-environment-with-commands), or [clone an existing environment](https://docs.conda.io/projects/conda/en/latest/user-guide/tasks/manage-environments.html#cloning-an-environment) and then modify it for your purposes.



## Helpful native Python functions
1. Loop Functions: useful when using `for` loops
- `zip`

  zip function zips two lists of the same length together so that you can iterate through both at the same time. 
  
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

    
- `zip` function is especially handy when plotting multiple subplots in one loop where you want to specify different axes labels, xticks, etc as you can zip these together and just iterate through once.

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


# Geographic information systems (GIS)
[QGIS](https://www.qgis.org/en/site/) is a great tool for working with spatial data, like rasters and shapefiles.  It's free and has a lot of capability.
