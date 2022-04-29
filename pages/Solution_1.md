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

for i in ${VAR}
    do
        wget ${URL}${i}.fasta

        cat ${i}.fasta >> muscle_input.fasta # write content of each fasta file to a single file
    done

#Use generated file to download muscle
muscle -align muscle_input.fasta -output muscle_output.afa
```

### and a python solution...

```python

#!/usr/bin/env python3

import wget
import os


URL = "http://www.uniprot.org/uniprot/"

with open("uniprot_IDs.txt","r") as file:
 	for line in file:
 		wget.download(URL + line + ".fasta")
 		

with open("muscle_py_input","w") as file2:
	for f in os.listdir():
		if f.endswith(".fasta"):
			with open(f) as fh:
				file2.writelines(fh)
```








