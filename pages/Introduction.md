# Introduction to Scripting with Bash

![](../assets/readme_img/scripting.jpg)

### What is a script?

A script is a text file living on the disk which has some text in it. This text is a series of commands which will be executed line by line in sequence. Importantly, when we run a script we are transfering the control of the system from the user to the script. The operating system will listen from the script and not from the command line. The scritps takes over.  

### Scripts vs Programs

Scripts do not do any significant computation on their own. Instead, they run "programs" that do the computational work. The job of a script is to **automate** and **document** the execution of commands/programs that were already created by others. 

the process of running programs. 

As a result, scripting languages do not need to be very efficient (they are orders of magnitude slower than compiled languages) so we can take advantage of it to write them in high level languages which are much easier to write, read and degub.

### What makes scrips useful and powerful?

**Efficiency** 

Automation of tasks makes work extremelly efficient. 

**Accuracy**

Typing the same commands over and over again is very prone to human error.

**Documentation**

A script become documentation of the work we performed on a machine. We have a record of the precise sequence of commands needed to **reproduce results**. 

### There are some special features in scripts:

Shibang line (tells the system how you want the script to be interpreted).

```bash
#!/bin/bash
```
It needs to be an executable.

```bash
echo ${PATH}
```

These are directories where the system expects to find executable files.
When we type:

```bash
ls
```
or 

```bash
cd
```

What we are doing is telling Bash to go and look for an executable with the name `ls` / `cd` somewhere in the PATH. 

If it gets to the end of the PATH without finding the executable we asked for:

```bash
"command not found"
```
**Note:** if we use `./` before the command, we  are dinamically adding that specific command to the PATH. 

### Into Scripting
The idea behind scripting is to provide us a means of not just running a single command, which we can easily do directly from the command line, but to run a series of commands automatically in a single process. We run a script, and the script runs the commands for us in the order we ask it for.

### A simple script

To run our very first script, we will take a couple of commands that are often used repetively in the command line and save them into a file so that we can use them later by typing **one single command**.

Move to `examples` directory and create a new file called `my_script.sh` using `nano`. 

We want our simple script to do two things:

1) print current working directory

2) count number of lines in a file

```bash
#!/bin/bash

pwd
wc -l "$1"
```

### Other features that make scripts powerful and versatile

* Variables
* Conditionals
* Parsing arguments into scripts

### Turing complete programming languages

If you want to write a programme that is able to achieve any computational task that you pass to it, the programming language has to be “Turing complete”.

Essencially, that means your programming language is capable of performing:

* conditional repetition.

* has readable and writable mechanisms of storage.

These features are what make a programming language “Turing complete”.

BASH and Python are “Turing complete” programming languages.

We can perform conditional repetition and we have a readable and writable storage mechanism within BASH and Python themselfs.

### Variables

Variables are a way of storing information within our programme. This information can be retrieved during the programme.

Bash has a very particular syntax to both define and retrieve variables.

```bash
#!/bin/bash
VAR="hello IGC"
echo ${VAR}
```
In UNIX, there are system variables that are already set for us: **environment variables**

```bash
echo ${PWD}
echo ${HOME}
echo ${PATH}
```

### Parsing arguments to scripts

We can change the behaviour of scripts without changing the script itself.

```bash
#!/bin/bash

VAR="hello world"
SLEEP=3

echo ${1}
echo ${2}
sleep $SLEEP
echo ${VAR}
```
Passing arguments to scripts can be extremelly useful to make them more configurable and usable.

```bash
#!/bin/bash

VAR="hello world"

echo ${1}
echo ${2}
sleep ${3}

echo ${VAR}
```

### For loops

For loops are what is called a **flow control structure** in programming. 

```bash
#!/bin/bash

for letter in a b c d
	do
		echo ${letter}
	done
```
The syntax and structure of a for loop does not change much. What we might change is the input for it and where we get those inputs from. 


## Exercise 1

**Intended learning outcomes:**

   * Using variables to store data such uniProt IDs and URL to get sequences from the web.
   * Use for loops to download fasta files associated with respective uniProt entry.
   * Use `wget` to retrieve files from web servers.
   * Concatenate multiple fasta files in a single file for downstream analysis.
   * Use output as input for another software down the pipeline. 


Write a script to download insulin protein sequences from varies species from uniPROT and use those sequences to build a multiple alignment using MUSCLE. The uniPROT entries are in a text file called `uniprot_ids.txt` in the `exercise_1`directory. 

[Solution for Exercise 1](Solution_1.md)

***********************************************************************
***********************************************************************

### Other things I need to touch before moving to exercise 2

**if/else statements**

**nested loops (loops inside loops)**

**reading and writing files in python**

**empty lists**

**append() function**

***********************************************************************
***********************************************************************


## Exercise 2

**Intended learning outcomes:**

* Getting data into python environment 
* Using python to filter data
* Using if/else statements 
* Using nested loops 
* Write data into files

When getting data from a sequencing facility, a common first task is to separate good and bad reads for downstream analysis. Keeping a good and clean FASTQ file reduces processing time and disk usage.
In this exercise we will write a python script to iterate over FASTQ files and filter reads according to their percentage of `NNNNNNs`.

[Solution for Exercise 2](Solution_2.md)









