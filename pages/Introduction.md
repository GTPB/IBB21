# Introduction to Scripting with Bash

![](../assets/readme_img/scripting.jpg)

### What is a script?

A script is a text file living on the disk which has some text in it. The text is a series of commands which must be run/executed from the command line.

 

### Scripts vs Programs

It is important to understad the difference between "scripts" and "real programs". Scripts do not do any significant computation on their own. Rather, scripts run "real programs" to do most of the computational work. The job of a script is to **automate** and **document** the process of running programs. 

As a result, scripting languages do not need to be very efficient (they are orders of magnitude slower than compiled languages) and they are generally **interpreted** rather than **compiled**.

Real programs, may be very large and computationally expensive and therefore they are written close to machine language. 

Since we are simply interested in **automating the execution of pre-existing commands or softwares**, picking up a scripting language and write a script will do the job just write. 

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

echo "The number of arguments is: ${#}"
echo "The list of arguments is: ${@}"
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

Write a script to download sequences from uniPROT and use those sequences to build a multiple alignment. The uniPROT entries are in a text file called `uniprot_ids.txt` in the `examples_dir`directory. 

By the end of this exercise you should able to:
    
   * Get uniProt IDs from `uniprot_ids.txt` and assign them to a variable.
   * Assign uniprot URL to another variable.
   * Use a for loop to download each fasta file associated with respective uniprot entry. 
   * Concatenate each fasta file downloaded into a single file to use as input. 
   * Use produced output for downstream analysis




```bash
#!/bin/bash

VAR=$(cat uniprot_ids.txt)

URL="http://www.uniprot.org/uniprot/"

for i in ${VAR}
    do
        echo "Downloading Uniprot entry: ${i}"
        wget ${URL}${i}.fasta
        echo "Done! Successfully downloaded ${i}"
    done
```

### and

```bash
#!/bin/bash

#!/bin/bash

# getting input data
VAR=$(cat uniprot_ids.txt)

URL="http://www.uniprot.org/uniprot/"

#download data
for i in ${VAR}
    do
        echo "Downloading Uniprot entry: ${i}"
        wget ${URL}${i}.fasta
        echo "Done! Successfully downloaded ${i}"

        cat ${i}.fasta >> muscle_input.fasta
        echo "File writen"
        rm ${i}.fasta
    done

sleep 2
echo "Starting Muscle"

#run muscle
muscle -align muscle_input.fasta -output muscle_output.afa
echo "Done!"
```














