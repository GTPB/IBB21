## Solution for Exercise 2

*1.1*
```python
#!/usr/bin/env python3

FASTA=open("2.fa","r")
```

*1.2*
```python
#!/usr/bin/env python3

FASTA=open("2.fa","r")

FASTA_Dict = {}
FASTA_header = ""
```

*1.3*
```python
#!/usr/bin/env python3

FASTA=open("2.fa","r")

FASTA_Dict = {}
FASTA_header = ""

for line in FASTA:
	if ">" in line:
		FASTA_header = line
		FASTA_Dict[FASTA_header] = ""
	else:
		FASTA_Dict[FASTA_header] = FASTA_Dict[FASTA_header] + line

```
*1.4*
```python
#!/usr/bin/env python3

FASTA=open("2.fa","r")

FASTA_Dict = {}
FASTA_header = ""


for line in FASTA:
	if ">" in line:
		FASTA_header = line
		FASTA_Dict[FASTA_header] = ""
	else:
		FASTA_Dict[FASTA_header] = FASTA_Dict[FASTA_header] + line

for sequence in FASTA_Dict.values():
	Perc_GC_Content = (sequence.count("G") + sequence.count("C")) /len(sequence) * 100

	print(FASTA_header + str(Perc_GC_Content))
```