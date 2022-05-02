# Introduction to Scripting 

![](../assets/readme_img/scripting.jpg)

### Why do we want to write scripts?

**Efficiency** 

Automation of tasks makes work extremelly efficient. 

**Accuracy**

Typing the same commands over and over again is very prone to human error.

**Documentation**

A script become documentation of the work we performed on a machine. We have a record of the precise sequence of commands needed to **reproduce results**. 

### What is a script?

A script is a text file living on the disk which has some text in it. This text is a series of commands which will be executed line by line in sequence. Importantly, when we run a script we are transfering the control of the system from the user to the script. The operating system will listen from the script and not from the command line. The scritps takes over.  

### Scripts vs Programs

Scripts do not do any significant computation on their own. Instead, they run "programs" that do the computational work. The job of a script is to **automate** and **document** the execution of programs that were already created by others. 

As a result, scripting languages do not need to be very efficient (they can be orders of magnitude slower than compiled languages) so we can take advantage of it and write them in scripting languages which are much more similar to human language. 


### There are some special features in scripts:

Special comment line (tells the system how you want the script to be interpreted).

```bash
#!/bin/bash
```
```python
#!/usr/bin/env python3
```
The script needs to be an executable:

1) Give executing permissions
```bash
chmod +x file_name
```

2) Give full path when executing script
```bash
./file_name
```

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

### Powerful and versatile

* Readable and writable mechanisms of storage
* Conditional repetition 
* Parsing arguments into scripts

BASH and Python allow us to perform conditional repetition and we have a readable and writable storage mechanism within BASH and Python themselfs.

### Variables

Variables are a way of storing information within our programme. This information can be retrieved during the programme.

bash and pyhthon have very simple ways of storing and retrieving info from variables.

```bash
#!/bin/bash

VAR="hello IGC"
echo ${VAR}
```
```python
#!/usr/bin/env python3

var = "hello IGC"
print(var)
```
### For loops
For loops are used when you want to repeat a block of code a fixed number of times. For loops are used in combination with an iterable data type.

```bash
#!/bin/bash

for l in a b c d
    do
        echo ${l}
    done
```
The syntax and structure of a for loop does not change much. What we might change is the input for it and where we get those inputs from. 

### Parsing arguments to scripts

We can make scripts more versatile, cofigurable and usable by parsing arguments to it. 

```bash
#!/bin/bash

VAR="hello world"
SLEEP=3

echo ${VAR}
sleep $SLEEP
echo ${1}
```

## Exercise 1

**Intended learning outcomes:**

   * Using variables to store uniProt IDs and URL to get sequences from the web.
   * Use for loops to download fasta files associated with respective uniProt entries.
   * Use `wget` to retrieve files from web servers.
   * Aggregate multiple fasta files in a single file for downstream analysis.
   * Use output as input for another software. 


Write a script to download insulin protein sequences from uniPROT and use those sequences to build a multiple alignment using MUSCLE. The uniPROT entries are in a text file called `uniprot_ids.txt` in the `exercise_1_Dir`directory. The url to get the sequences from Uniprot is: 
`http://www.uniprot.org/uniprot/`

[Solution for Exercise 1](Solution_1.md)

***********************************************************************
***********************************************************************

## Exercise 2

GC content is informative in several ways. Higher GC content levels indicates a relatively higher melting temperature in molecular biology, and DNA sequences that encode proteins tend to be found in GC-rich regions of the genome. Filter data from seq facility according to GC content. Low GC content no conding sequences. 

***********************************************************************
***********************************************************************

### Other things I need to touch before moving to exercise 2

**if/else statements**

**nested loops (loops inside loops)**

**reading and writing files in python**

**empty lists**

**objects and methods**

***********************************************************************
***********************************************************************


## Exercise 3

**Intended learning outcomes:**

* Getting data into python environment 
* Using python to filter data
* Using if/else statements 
* Using nested loops 
* Write data into files

When getting data from a sequencing facility, a common first task is to separate good and bad reads for downstream analysis. Keeping a good and clean FASTQ file reduces processing time and disk usage.
In this exercise we will write a python script to pre-process FASTQ files and filter reads according to their percentage of `NNNNNNNs`.

An “N” means that the Illumina software was not able to make a basecall for this base. 


[Solution for Exercise 2](Solution_2.md)




















