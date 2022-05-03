## Solution for Exercise 1

*1.1*
```bash
#!/bin/bash

# cat writes the content of uniprots_ids.txt to VAR
VAR=$(cat uniprot_ids.txt)

# Assings uniprot URL to the variable URL
URL="http://www.uniprot.org/uniprot/"

# for loop that will iterate over VAR and download a fasta file on each iteration of the loop
for ID in ${VAR}
    do
        wget ${URL}${ID}.fasta
    done
```

*1.2*
```bash
#!/bin/bash

VAR=$(cat uniprot_ids.txt)

URL="http://www.uniprot.org/uniprot/"

for entry in ${VAR}
    do
        wget ${URL}${entry}.fasta

        cat ${entry}.fasta >> muscle_input.fasta 
    done

muscle -align muscle_input.fasta -output muscle_output.afa
```










