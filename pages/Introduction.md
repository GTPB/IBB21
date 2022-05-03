# Introduction to Scripting 

![](../assets/readme_img/binary_dna.jpg)

### Why writing scripts?

**Efficiency** 

Automation of tasks makes your work extremelly efficient. 

**Accuracy**

Typing the same commands over and over again is very prone to human error.

**Reproducibility**

A script becomes documentation of the work we performed on a machine. We have a record of the precise sequence of commands needed to **reproduce results**. 

### What is a script?

A script is a text file living on the disk which has some text in it. Importantly, this text is a series of commands which will be executed line by line in sequence. When we run a script we are transfering the control of the system from the user to the script. The operating system will listen from the script and not from the command line. The script takes over.  

### Scripts vs Programs

Scripts do not do any significant computation on their own. Instead, they run "programs" that do the computational work itself. The job of a script is to **automate** and **document** the execution of programs that were already created by others. 

As a result, scripting languages do not need to be very efficient (they can be orders of magnitude slower than compiled languages) so we can take advantage of it and write them in scripting languages which are much easier to write, read and debug.  


### There are some special features in scripts:

Special comment line (tells the system how you want the script to be interpreted).

```bash
#!/bin/bash
```
```python
#!/usr/bin/env python3
```
The script needs to be an executable:

1) Give executing permissions:
```bash
chmod +x file_name
```

2) Give full path when executing script:
```bash
./file_name
```

### Into Scripting
The idea behind scripting is to provide us a means of not just running a single command, which we can easily do directly from the command line, but to run a series of commands automatically in a single process. We run a script, and the script runs the commands for us in the order we ask it for.

### A simple script

To run our very first script, we will take a couple of commands that are often used repetively in the command line and save them into a file so that we can use them later by typing **one single command**.

Move to `Desktop/Scripting/exercise_1_Dir` and create a new file called `my_script.sh`. 

We want our simple script to do two things:

1) print current working directory

2) count number of lines in a file

```bash
#!/bin/bash
echo "hello IGC"
pwd
ls -l
sleep 3
echo "I am done..."
```

### Powerful and versatile scripts

* Readable and writable mechanisms of storing information
* Conditional repetition 
* Passing arguments into scripts

BASH and Python allow us to perform conditional repetition, both have readable and writable mechanisms of storage and have ways of passing arguments ro scripts.

### Variables

Variables are a way of storing information within our programme. This information can be retrieved during the programme execution. 

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

for element in a b c d
    do
        echo ${element}
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
sleep ${SLEEP}
echo ${1}
```

## Exercise 1

**Intended learning outcomes:**

Write a script to download insulin protein sequences from uniPROT and use those sequences to build a multiple alignment using MUSCLE. The uniPROT entries are in a text file called `uniprot_ids.txt` in the `exercise_1_Dir`directory.


**url:**`http://www.uniprot.org/uniprot/`

**Intended learning outcomes:**

   * Using variables to store uniProt IDs and URL to use down the script.
   * Use a for loop to download fasta files associated with respective uniProt entries.
   * Use `wget` to retrieve files from web servers.
   * Aggregate multiple fasta files in a single file for downstream analysis (MUSCLE input).
   * Use generated output as input for muscle 

[Solution for Exercise 1](Solution_1.md)

***********************************************************************
***********************************************************************

###


###


###


###

## Exercise 2

GC content is informative in several ways. For example, higher GC content levels indicate a relatively higher melting temperature in molecular biology. Also, DNA sequences that encode proteins tend to be found in GC-rich regions of the genome. A common task in bioinformatics is to extract contigs with a GC content percentage bellow a certain value. 
In this exercise we will write a python script that will scan fasta files and output the percentage of GC content on each contig to the user.

**Intended learning outcomes:**
*
*
*
*

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




















