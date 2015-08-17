---
coursetitle: Introduction to High Performance Computing
layout: page
title: Course Exercises
---
 
## Practice Session 1

 *   Start an interactive session on iceberg using the Sun Global Desktop
 *   Start a file transfer client and move files to and from iceberg
 *   Extract the course examples, change directory to a directory you will be using for the course and type
~~~ {.bash}
 tar –zxvf /usr/local/courses/hpc_intro.tgz
~~~
                   

> ## Case Study {.challenge}
>
> We are studying inflammation in patients who have been given 
> a new treatment for arthritis we need to analyze the firts sets of inflammation data.
> The data sets are held in comma separated variable (csv) format. Each row holds
> the observations for one patient. Each column holds the inflammation measured in one day.

## Practice Session 2
### Running Applications on the HPC Cluster

For this practice session we will run the R application
The lastest version of R can be loaded with

~~~{.bash}
 module load apps/R/3.2.0
~~~

R can then be run with

~~~{.bash}
 $ R
~~~

~~~{r,include=FALSE}
 dat <- read.csv(file = "../data/inflammation-01.csv", header = FALSE)
 avg_day_inflammation <- apply(dat, 2, mean)
 plot(avg_day_inflammation)
~~~

to exit R type 

~~~{r,echo=FALSE}
 q()
~~~

Further details on R at
[R documentation for iceberg](http://rcg.group.shef.ac.uk/iceberg/software/apps/R.html)





> ## Case Study {.challenge}
>
> We will run a series of simulations of Fish populations.
> 
> Thisa artificial program calculates the effect of quotas on the fish stocks.
> We will practice using Sun Grid Engine by running this
> technically simple problem, the politicians prefer us
> not to know about!

## Practice Session 3

### Submitting jobs to Sun Grid Engine
From the course directory
~~~ {.bash}
 cd sge
~~~

From an interactive session
 * Load the compiler module
 * Compile the fish program
 * Run test1, test2 and test3

Compile the program using the fortran compiler

First load the compiler module
~~~ {.bash}
 module load compilers/intel/14.0
~~~


Compile the fish program
~~~ {.bash}
 ifort fish.f90 -o fish
~~~

 
 Start with test1 which is a simple job script. 
 Submit test1 to the batch queue and use qstat to follow 
 its progress.
 
 After running the test1 script have a look at all the 
 other test* scripts in the numeric order. 
 It is important that you follow the numeric order as
 the problems build up using the previous solutions. 
 The comments in each script file tells you what to do next.

 This directory contains an artificial program that 
 calculates the effect of quotas on the fish stocks.
 We will practice using Sun Grid Engine by running this
 technically simple problem, the politicians prefer
 not to know about! The program is named fish and resides
 in this directory.
 
 When you come to test 3, 

  Your task is to run the fish program under SGE using qsub. 
  The following steps are advisable: 
  * Run the program interactively to see what it does 
      and what input it expects from the user.
  * Create an input file which will contain the 
      expected input data ' that you would normally 
      enter at the keyboard'.
  * Prepare a job submission script which will 
        * read the data from your input file
        * write the results into a job output file or another file of your choice.
  * Submit the script to SGE.
  * Add commands to join the error and normal output into one single file
      and also to email you about the progress of your job. 

## Practice Session 4

### Submitting a Task Array

Continuing with the fish population program


Run the SGE task array example
Run test4, test5


















## Resource Links

*   [Shared Notepad](https://etherpad.mozilla.org/CzIWonFrAs)
*   [Course Examples](http://rcg.group.shef.ac.uk/courses/hpcintro/downloads/hpc_intro.tgz)

