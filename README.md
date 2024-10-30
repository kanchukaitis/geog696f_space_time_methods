# GEOG696F Python for Spatial and Temporal Data Science 

## Overview
This is a graduate statistics and programming course taught as GEOG696F, the '**Advanced Methods and Techniques**' seminar in the School of Geography, Development, and Environment) at the University of Arizona.  The class was first taught in Fall 2024.  The full syllabus is available [here](https://github.com/kanchukaitis/geog696f_space_time_methods/blob/main/geog696f_syllabus.pdf).

This course is designed as a graduate level class in a workshop format to give students a theoretical framework, practical experience, expert knowledge, and statistical tools for analyzing datasets that have a temporal and/or spatial dimensions. It is fundamentally about [building tools](https://agupubs.onlinelibrary.wiley.com/doi/full/10.1029/2011EO500010) and practical understanding so that students can knowledgeably apply these techniques in their own research and their own data.  Topics include: basic and intermediate tools and procedures in Python, correlation, regression, Monte Carlo methods, time series analysis, spectral analysis, reduced space empirical orthogonal function/principal components analysis, interpolation, Gaussian processes, and Bayesian statistics.  The course encompasses instruction and training in Python and in the use and manipulation of large multi-dimensional datasets.

The major outcome for the class for each student will be a new and independent analysis of a substantial dataset using one or preferably more techniques from the course materials, a formal manuscript describing the motivation, methods, and results of this analysis, and a professional oral presentation.  Students are encouraged to bring with them or seek out data relevant to their research to use for their final project.  Ideally, students' final projects will provide the material for a thesis chapter and/or peer-reviewed article. 

## General Schedule

Augst 26 to September 4 - [Python fundamentals](https://github.com/kanchukaitis/geog696f_space_time_methods/tree/main/01_python_fundamentals)

September 9 to September 11 - [Correlation](https://github.com/kanchukaitis/geog696f_space_time_methods/tree/main/02_correlation)

September 16 to September 18 - [Monte Carlo and stochastic simulation](https://github.com/kanchukaitis/geog696f_space_time_methods/tree/main/03_monte_carlo)

September 23 to September 25 - [Regression](https://github.com/kanchukaitis/geog696f_space_time_methods/tree/main/04_regression)

September 30 to October 2 - [Time series analysis](https://github.com/kanchukaitis/geog696f_space_time_methods/tree/main/05_time_series)

October 7 to October 9 - [Spectral analysis](https://github.com/kanchukaitis/geog696f_space_time_methods/tree/main/06_spectral_analysis)

October 14 to October 16 - [Reduced space methods](https://github.com/kanchukaitis/geog696f_space_time_methods/tree/main/07_reduced_space)

October 21 to October 23 - [Interpolation](https://github.com/kanchukaitis/geog696f_space_time_methods/tree/main/08_interpolation) and [Gaussian Processes](https://github.com/kanchukaitis/geog696f_space_time_methods/tree/main/09_gaussian_processes)

October 28 to October 30 - Introduction to Bayesian statistics

November 4 to November 29 - Student project work

December 2 to December 4 - Final presentations

December 13 - Final project and paper due

 
## Why Python? 
My own programming career started in FORTRAN and moved to MATLAB, a language I've now spent almost 25 years using effectively and (mostly) without complaint.   But with an increasing number of jobs for graduate students **outside** academia and with the rise of Python as the _de facto_ language of data science, I've start to teach my data anlysis classes in Python.  This had involved some growing pains (for me!), but in the end I hope that the chance to learn statistical techniques in a language so widely used across so many fields will be worth the extra trouble for the students who take the class.  Particularly for earth and environmental scientists relatively new to Python, Martin Trauth's book [Python Recipes for Earth Sciences](https://link.springer.com/book/10.1007/978-3-031-07719-7) provides a useful and broad introduction solidly grounded in various types of analyses.  

## Recommended Software Installation 
[Anaconda](https://www.anaconda.com/download) is a package management software that downloads a number of packages for data analysis and exploration – including base Python – but is quite large.  Since not all packages are always required, a 'lite' version of Anaconda is also available called [Miniconda](https://docs.conda.io/projects/miniconda/en/latest/miniconda-install.html).  Miniconda gives you base Python and allows for all the Anaconda management functions, but has a much smaller initial download size and installation time because it installs few packages (which means you'll need to install some packages not included in the installation). Once installed, both Anaconda or Miniconda will be referred to (and called from the shell, terminal, or command line) simply as `conda`.  A cheatsheet of `conda` commands can be found [here](https://conda.io/projects/conda/en/latest/user-guide/cheatsheet.html). 

I personally use Anaconda, but instructions for installing via either are available in the following links:

[This page from DataCamp](https://www.datacamp.com/blog/how-to-install-python) contains useful and straightforward information on getting Python installed on both Windows and Mac. 

[Here is an installation narrative we developed for a coding bootcamp](https://github.com/kanchukaitis/geog696f_space_time_methods/blob/main/geog696f_installation_narrative.md) - it includes step-by-step instructions for installation using Miniconda as well as how to setup a virtual conda environment for this class, if you so choose.  There is a 17 minute [YouTube video](https://www.youtube.com/watch?v=PDZDK6QQ1q4) to accompanies this, which shows you step-by-step instructions as well (note you won't need to do everything in the video). 

[This Youtube video](https://www.youtube.com/watch?v=h1sAzPojKMg&ab_channel=VisualStudioCode) from Visual Studio Code (the integrated coding environment we'll use in this class) can get you up and running pretty quickly. They show installation in Windows, so macOs will be slightly different.  If necessary, we'll also go this **live** in class the week of August 26th. 

Here are the basic steps from the video:
* Install Python using Miniconda (recommended for this class: https://docs.conda.io/en/main/miniconda.html) or the full individual Anaconda distribution (https://www.anaconda.com/download) for your operating system.  Both are free.  **Note that if you have an older operating system, the current versions of Miniconda might not work on your system.**  A simple comparison of the benefits and drawbacks of Anaconda vs. Miniconda can be found [here](https://www.earthdatascience.org/workshops/setup-earth-analytics-python/setup-git-bash-conda/).
* For Windows users: from the newly installed Conda prompt or from within Python [install iPython](https://ipython.readthedocs.io/en/stable/install/install.html#quick-install).
* Install Juypter Notebooks: https://jupyter.org/install
* Install Visual Studio Code itself (https://code.visualstudio.com/download) for your system
* Within Visual Studio Code, install the Python extensions (from Microsoft)
* Test your system 

## Integrated Development Environments (IDE)

Unlike MATLAB and R (via RStudio), there is no single software package used for Python development.  Indeed, you could develop Python with just text files and the command line.  In this class I will used [VS Code](https://code.visualstudio.com/), a free and multi-languages IDE.  You can also develop your code entirely in [Jupyter notebooks in your browser](https://www.codecademy.com/article/how-to-use-jupyter-notebooks) if you wish.  Another popular IDE is [PyCharm](https://www.jetbrains.com/pycharm/), which is excellent but not free.  Finally, there is now [Positron](https://github.com/posit-dev/positron), from the makers of RStudio - it is still in development, but looks promising. 

It isn't important which IDE you choose. 

## Running notebooks in your browser

You can find step-by-step instructions for running Jupyter notebooks locally in your browser [here](https://docs.jupyter.org/en/latest/running.html)

## Getting Started with Python

If you'd like some additional materials for getting started with Python, here are some possibilities:

- DataCamp has many good online courses, which you can often get for free, including [Introduction to Python](https://www.datacamp.com/courses/intro-to-python-for-data-science), [Intermediate Python](https://www.datacamp.com/courses/intermediate-python), and [a whole lot more](https://www.datacamp.com/category/python?showAll=true).
- There is a Software Carpentries [introductory Python tutorial](https://swcarpentry.github.io/python-novice-gapminder/)
- University of Helsinki offers a [free online MOOC on Introduction to Python](https://programming-23.mooc.fi/)
- Harvard's [CS50 Introduction to Programming with Python](https://cs50.harvard.edu/python/2022/) from 2022 is available online for free 

## Github

Although not strictly required for this course, I encourage you to use the capacity of Git and Github to streamline your access to and use of the notebooks created for this class, as well as advance your own development of reproducible and readily shareable code.  Here are some good places to start:

* Software Carpentry's [Version Control with Git](https://swcarpentry.github.io/git-novice/)
* Jonathan King's [Github Tutorial](https://jonking93.github.io/Github-Tutorial-Workshop/workshop/welcome). 

## Contact

Did you find this course material useful?  Want to share ideas?  Find some bugs? Feel free to contact me at [kanchukaitis@arizona.edu](mailto:kanchukaitis@arizona.edu)
