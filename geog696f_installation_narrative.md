# Getting started with Python and Jupyter Notebooks

## Index

- [Step-by-step walkthough](#a-complete-walkthrough-installation)
- [Summary](#setup-commands-summary)
- [Integrated Development Environments](#integrated-development-environments)
 
## A complete walkthrough installation 

This document is going to cover the essential setup for Python and Jupyter Notebooks.  You may optionally wish to setup a specific virtual environment for the class. 

**Required software:**

- Python!  We recommend using [Anaconda](https://anaconda.org/): a package management software primarily for Python. You can also use [Miniconda](https://docs.conda.io/projects/miniconda/en/latest/), which is a minimal installer that allows users to more selectively install only the packages they need. We *do not* recommend using Homebrew if you are on macOS.
- [Pip](https://pip.pypa.io/en/stable/) is the default package installer for Python, enabling users to easily download and install additional packages from the ‘Python Package Index’ ([PyPI](https://pypi.org/)). Pip will be installed automatically when you install Anaconda or Miniconda. 
- [Jupyter](https://jupyter.org/): an open-source platform that facilitates interactive computing by providing a web-based interface for creating and sharing documents containing live code. Jupyter is installed with Anaconda, but would need to be added to Miniconda (see below). 

These software packages are used in order to ensure that packages and code shared between collaborators are up to date and usable across Operating Systems (OS).

**Anaconda vs Miniconda for Python**

Anaconda is a package management software that downloads a number of packages for data analysis and exploration – including base Python – with a total size of ~3GB. Since not all packages are always required, a “lite” version of Anaconda is also available: Miniconda. Miniconda gives you base Python and allows for all Anaconda functions, but has a much smaller download size (~500MB) and installation time because it installs few packages. Once installed, both Anaconda or Miniconda will be referred to (an can be called from the command line) simply as “conda”.

**I’m on a Mac, why can’t I use the pre-installed Python from macOS?**

macOS does come with a preinstalled version of Python (although typically lagging behind the latest version). However, it is used behind the scenes as part of the operating system, so modifying or updating this could have unintended consequences for the rest of your system and programms.  It is much safer to install a version from Anaconda or Miniconda as described here and use this for coding.

** Installing Anaconda **

The instructions for installing Anaconda can be found [here](https://docs.anaconda.com/anaconda/install/).  The instructions are quite good. 

**Installing via Miniconda **

If you elect to install Miniconda instead of Anaconda, please go to the following page and download and then execute the correct file for your OS: [https://docs.conda.io/projects/miniconda/en/latest/](https://docs.conda.io/projects/miniconda/en/latest/)

Notes:

- Mac users: downloading either the bash or pkg versions should yield the same result, Downloading the pkg will allow you to install conda by clicking through an installer, whilst downloading the bash version will require you to execute the downloaded script.
- Windows users: downloading the Miniconda installer will result in a command prompt named “Anaconda”. This is where you will be able to access all of your conda installations. Packages installed through the conda command prompt are **NOT** available in PowerShell and/or other installed shells (e.g., git shell).
- [https://docs.anaconda.com/free/anaconda/getting-started/](https://docs.anaconda.com/free/anaconda/getting-started/) is a great starting point for learning about conda!
- Conda is used exclusively through the command line, therefore you should be comfortable using the shell (or the terminal in macOS). The Carpentries offer [an Open Source tutorial on using the shell](https://swcarpentry.github.io/shell-novice/)

Once Miniconda is installed, access your terminal (or, for Windows users search '`Anaconda Prompt`’). You can check your install by typing ‘conda list’ in the terminal, which will reveal the location of your conda and the packages that are currently installed with it. 

**Understanding conda and creating environments (optional) **

As a package manager, conda (no matter which way you installed it) allows you to have different packages and different versions of packages inside a given environment. The (base) you see on the left of the prompt means that you are now in the “base” environment. Following are a number of commands correlated to creating, activating, installing and deleting packages and environments.

- Creating an environment: `conda create --name your\_environment\_name` 
  - When creating a completely new environment, you may want to also include the python version. Use the following example: 

`conda create --name geog696f python=3.11`

Above we specify the Python version 3.11, which is recent but not 'cutting edge'.  This doesn’t mean that the packages and libraries we'll use don’t work with other versions (indeed, we know most of them will), but this can be good practice to ensure everything works as intended and avoid dependency problems (more on this in class). Note also that when you create this environment the first time, conda will very likely install several additional packages.  This is normal and might take a few minutes. 

- Activating an environment: `conda activate your\_environment\_name`
  - After creating an environment, we also first need to activate it. In our case, the command to do this is:

`conda activate geog696f`

We are now ‘inside’ the geog696f environment we created, and importantly anything we install while we’re here will go into this environment only. 

- Installing a package: `conda install -c channel\_name package\_name`
  - This command will install a specific package from a specific channel (-c). Channels are a repository or collection of software packages that can be accessed and used by Conda package manager to install, update, and manage software dependencies in a Conda environment. We will use this functionality below.

Other useful commands:

- Deactivating an environment: `conda deactivate`
  - This will deactivate your current environment. All of your packages and versions will be available again if you activate it again.
- Listing environments: `conda env list`
  - This will list all of the environments available on your machine
- Listing all packages within an environment: `conda list`
  - This will print (show) all the packages in the current environment, as well as version and channel of origin 

**Why use separate environments in Python instead of just the base Python?** 

(Virtual) environments are isolated sets of code where all the packages and the specific program versions you install only apply when you are operating in that environment.  This allows you to enter an environment and install and run a specific set of packages without worrying that they might conflict somehow with other packages you have installed for other projects or will install in the future.  This also prevents later updates to Python and its packages and libraries from breaking your current workflow.  While it is likely you could use your base Python environment successfully when you are just getting started, the longer you work in Python the greater chance that conflicts between packages and Python versions might disrupt your specific projects or coursework.  So, getting used to using virtual environments now is a good practice for the future.  

**Understanding and Installing Jupyter and Jupyter Notebook**

Jupyter is an open-source project that provides a web-based interactive computing platform, allowing users to create and share documents containing live code, equations, visualizations, and narrative text. The term "Jupyter" derives from three core programming languages it supports: Julia, Python, and R.

A Jupyter Notebook is a specific application of the Jupyter project that allows users to create and share documents with a mix of live code, equations, visualizations, and narrative text in a web-based interface. It supports multiple programming languages, making it a versatile tool for data analysis, scientific research, and education.

Anaconda should automatically install everything you need (although the below is a good guide if something goes wrong). If you elected to install Miniconda, you need to install Jupyter and Jupyter notebooks, so open the terminal and in the conda environment you created, execute the following: 

`conda install notebook`

When prompted for a y/n, type y. All of the packages and required dependencies will be automatically downloaded and installed and this may take a minute. 

Once installed, in order to access Jupyter Notebook, from your terminal type:

`jupyter notebook`

A new tab from your default internet browser will open, presenting you with a Jupyter window. The window will display the contents of the folder you were in when you made the call from the command prompt (in many cases, this will be your home directory). Here you can create Jupyter Notebooks as well as navigate directories and access existing files.

There might be an issue where if Jupyter isn’t able to automatically recognize your “dplpy” named environment. If that happens, you will be required to execute the following steps before running jupyter notebook:

1. Install ipykernel: `pip install ipykernel`
1. Make kernel discoverable by Jupyter: `python -m ipykernel install --user --name dplpy --display-name "dplpy"`

## Setup Commands Summary for Miniconda:

1. Install conda using the correct installation release for your software from [https](https://docs.conda.io/projects/miniconda/en/latest/)[://](https://docs.conda.io/projects/miniconda/en/latest/)[docs](https://docs.conda.io/projects/miniconda/en/latest/)[.](https://docs.conda.io/projects/miniconda/en/latest/)[conda](https://docs.conda.io/projects/miniconda/en/latest/)[.](https://docs.conda.io/projects/miniconda/en/latest/)[io](https://docs.conda.io/projects/miniconda/en/latest/)[/](https://docs.conda.io/projects/miniconda/en/latest/)[projects](https://docs.conda.io/projects/miniconda/en/latest/)[/](https://docs.conda.io/projects/miniconda/en/latest/)[miniconda](https://docs.conda.io/projects/miniconda/en/latest/)[/](https://docs.conda.io/projects/miniconda/en/latest/)[en](https://docs.conda.io/projects/miniconda/en/latest/)[/](https://docs.conda.io/projects/miniconda/en/latest/)[latest](https://docs.conda.io/projects/miniconda/en/latest/)[/](https://docs.conda.io/projects/miniconda/en/latest/)
2. Create a new environment: `conda create --name geog696f python=3.11`
3. Activate your newly created environment: `conda activate geog696f`
4. Install Jupyter/Notebook: `conda install notebook`
5. Execute Jupyer notebook: `jupyter notebook`
   5a. If “geog696f” environment is not recognized by jupyter (happens for some operating systems), do the following before executing jupyter notebook:
      5a1. Install ipykernel: `pip install ipykernel`
      5a2. Make kernel discoverable by Jupyter: `python -m ipykernel install --user --name geog696f --display-name "geog696f"`


## Integrated Development Environments

While Jupyter notebooks can be used locally via your web browser, there are several Integrated Development Environments (IDEs) that are popular as well.  Unlike R (R Studio) and MATLAB, there is no single IDE for Python, but your instructor will be mostly using [Virtual Studio Code (VS Code](https://code.visualstudio.com/)[://](https://code.visualstudio.com/)

VS Code is free and has extensions to help you code in Python (or almost any other language as well).  
