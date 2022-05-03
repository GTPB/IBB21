## Solution for Exercise 1

*1.1*
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










