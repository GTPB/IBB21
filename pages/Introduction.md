# Introduction to Scripting

![](../assets/readme_img/IGC_Tower_DSCF7958_ed.webp)

### Why writing scripts?

fgdfgdfgdfgdfg
gfd
gdfgdfgdfs
**Efficiency**

Automation of tasks enhances resource usage and reduces time consumption.

**Accuracy**
Typing the same commands over and over again is very prone to human error. Scripts allow the same method to be used extensively.

**Reproducibility**

A script becomes documentation of the work we performed on a machine. We have a record of the precise sequence of commands needed to **reproduce results**.

### What is a script?

A script is a text file living on the disk which has some text in it. Importantly, this text is a series of commands which will be executed line by line in the sequence we ask it for. When we run a script we are transfering the control of the system to the script. The operating system will listen from the script and not from the user. The script takes over.

### Scripts vs Programs

Scripts do not do any significant computation on their own. Instead, they run "programs" that do the computational work. The job of a script is to **automate** and **document** the execution of programs that were already created by others.

As a result, scripting languages do not need to be very efficient so we can take advantage of that by writing scripts in languages that are closer to human language and therefore much easier to write, read and debug.

### There are some special features in scripts:

Special comment line (tells the system how you want the script to be interpreted).

```bash
#!/bin/bash
```

or

```python
#!/usr/bin/env python3
```

The script needs to be an executable:

1. Give executing permissions:

```bash
chmod +x file_name
```

2. Provide full path when running the script:

```bash
./file_name
```

### Into Scripting

The idea behind scripting is to provide us a means of not just running a single command, which we can easily do directly from the command line, but to run a series of commands automatically in a single process. We run a script, and the script runs the commands for us in the order we ask it for.

### A simple script

To run our very first script, we can take a couple commands and save them into a file so that we can run them in **one single command**.

Create a new file called `my_script.sh` and write the following script:

```bash
#!/bin/bash
echo "hello IGC, I'll be back in 5 seconds..."
sleep 5
echo "I am back"
```

### More powerful and versatile scripts

- Readable and writable mechanisms of storing information
- Conditional repetition
- Passing arguments into scripts

BASH and Python allow us to perform conditional repetition, have readable and writable mechanisms of storage and have ways of passing arguments to scripts.

### Variables

Variables are a way of storing information within our programme. This information can be retrieved during the programme execution.

bash and python have very simple ways of storing and retrieving info to/from variables.

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

### Passing arguments to scripts

We can make scripts more versatile, configurable and usable by parsing arguments to it.

```bash
#!/bin/bash

sum=$(($1 + $2))
echo "Sum = $sum"
```

## Exercise 1

Write a script to retrieve a set of insulin protein sequences from uniPROT and use those sequences to build a multiple alignment using MUSCLE. The uniPROT entry names are in a text file called `uniprot_ids.txt` in the `exercise_1_Dir`directory.

**url:**`http://www.uniprot.org/uniprot/`

**Intended learning outcomes:**

- Using variables to store uniProt IDs and URL to use down the script.
- Use a for loop to download fasta files associated with respective uniProt entries.
- Use `wget` to retrieve files from web servers.
- Aggregate multiple fasta files in a single file for downstream analysis (MUSCLE input).
- Use generated output as input for muscle.

[Solution for Exercise 1](Solution_1.md)

---

---

## Python

### Object methods

Python objects have methods (functions) that are defined for specific data types.

```python
#!/usr/bin/env python3
x = "atgcggcctagagctgatttgcgc"
print(type(x))
print(x.upper())
print(x.count("g"))
```

```python
#!/usr/bin/env python3
x_list = [4,24,3,14,5]
print(type(x_list))
x_list.append(9)
x_list.sort()
```

### Reading files in python

```python
#!/usr/bin/env python3
FILE_X = open("one.fa","r")

# FILE_X.read()
# FILE_X.readlines()
# FILE_X.readline()

for line in FILE:
    print(line)

FILE.close()
```

### Writing files in python

```python
#!/usr/bin/env python3
FILE2 = open("XXX.txt","w")

FILE2.write("hello IGC")

FILE2.close()
```

### Dictionaries

Dictionaries are data types that allow us to associate a **key** to a **value**.

```python
#!/usr/bin/env python3
my_dictio = {"header_1":"ATAGCTGC", "header_2":"GGTAGATA","header_3":"GTGATAGA"}

print(my_dictio)
print(my_dictio.items())
print(my_dictio.keys())
print(my_dictio.values())
```

### if/else logical statements

Allow to control the flow of the script. The `if` keyword followed by an expression defines a block of code that will only be executed if that statement is `True`.

```python
#!/usr/bin/env python3

header = ">sp|Q09167|"

for element in header:
    if element == ">":
        print("Yes")

    else:
        print("No")
```

## Exercise 2

GC content is informative in several ways. Higher GC content levels indicate a relatively higher melting temperature in molecular biology. Also, DNA sequences that encode proteins tend to be found in GC-rich regions of the genome. A common task in bioinformatics is to extract contigs with a GC content percentage bellow a certain value.
In this exercise we will write a python script that scans fasta files and outputs the percentage of GC content on each contig.

**Intended learning outcomes:**

- Reading and writing files
- Using methods in python
- Using empty data structures to populate with output of loops
- Using if/else statements to separate headers from sequences in fasta files

[Solution for Exercise 2](Solution_2.md)

---

---

### enumerate() function

A foor loop usually aims to iterate over an iterable object. That means we usually don't need a counting variable to access elements of the iterable. Sometimes, however, we might want to have a variable that changes on each loop iteration. By using `enumerate()` we get a **counter** and the **value** of the iterable at the same time.

```python
#!/usr/bin/env python3

a_list = ["ATGCTGA","ATGATGCT","GGTAGTTGA","ATAGCTGA"]

for index, sequence in enumerate(a_list):
    print(index,sequence)
```

### nested loops (loops inside loops)

```python
#!/usr/bin/env python3

list_x = ["ATGCTGA","ATGATGCT","GGTAGTTGA","ATAGCTGA"]

for line in list_x:
    for letter in line:
        print(letter)
```

---

---

## Exercise 3

When getting data from a sequencing facility, a common first task is to separate good and bad reads for downstream analysis. Keeping a good and clean FASTQ file reduces processing time and disk usage.
In this exercise we will write a python script to pre-process FASTQ files and filter reads according to their percentage of `NNNNNNNs`. An “N” means that the Illumina software was not able to make a basecall for this base.

**Intended learning outcomes:**

- Getting data into python environment
- Using python to filter data
- Using if/else statements
- Using nested loops
- Write data into files

[Solution for Exercise 3](Solution_3.md)
