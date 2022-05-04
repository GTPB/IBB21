
## Solution for Exercise 3

*1.1*
```python
#!/usr/bin/env python3
F = open("SRR_test.fastq","r")


F.close()
```

*1.2*
```python
#!/usr/bin/env python3
F = open("SRR_test.fastq","r")

seq_line = 1
reads = []
good_reads = []
bad_reads = []

F.close()
```

*1.3*
```python
#!/usr/bin/env python3
F = open("SRR_test.fastq","r")

seq_line = 1
reads = []
good_reads = []
bad_reads = []

for line in F:
    reads.append(line)


F.close()
```

*1.4*
```python
#!/usr/bin/env python3
F = open("SRR_test.fastq","r")

seq_line = 1
reads = []
good_reads = []
bad_reads = []

for line in F:
    reads.append(line)

for index,line in enumerate(reads):

    if index == seq_line:
        if line.count("N") > 10:
            bad_reads.append(reads[seq_line-1:seq_line+3])
        else:
            good_reads.append(reads[seq_line-1:seq_line+3])

F.close()
```
*1.5*
```python
#!/usr/bin/env python3
F = open("SRR_test.fastq","r")

seq_line = 1
reads = []
good_reads = []
bad_reads = []

for line in F:
    reads.append(line)

for index,line in enumerate(reads):

    if index == seq_line:
        if line.count("N") > 10:
            bad_reads.append(reads[seq_line-1:seq_line+3])
        else:
            good_reads.append(reads[seq_line-1:seq_line+3])

        seq_line = seq_line + 4
          
F.close()
```
*1.6*
```python
#!/usr/bin/env python3
F = open("SRR_test.fastq","r")

seq_line = 1
reads = []
good_reads = []
bad_reads = []

for line in F:
    reads.append(line)

for index,line in enumerate(reads):

    if index == seq_line:
        if line.count("N") > 10:
            bad_reads.append(reads[seq_line-1:seq_line+3])
        else:
            good_reads.append(reads[seq_line-1:seq_line+3])

        seq_line = seq_line + 4

f_bad = open("wed_bad.fastq","w")
for line in bad_reads:
    for element in line:
        f_bad.write(element)
        
F.close()
```
*1.7*
```python
#!/usr/bin/env python3
F = open("SRR_test.fastq","r")

seq_line = 1
reads = []
good_reads = []
bad_reads = []

for line in F:
    reads.append(line)

for index,line in enumerate(reads):

    if index == seq_line:
        if line.count("N") > 10:
            bad_reads.append(reads[seq_line-1:seq_line+3])
        else:
            good_reads.append(reads[seq_line-1:seq_line+3])

        seq_line = seq_line + 4

F_bad = open("wed_bad.fastq","w")
for line in bad_reads:
    for element in line:
        F_bad.write(element)
        
F.close()
F_bad.close()
```
*1.8*
```python
#!/usr/bin/env python3

F = open("SRR_test.fastq","r")

seq_line = 1
reads = []
good_reads = []
bad_reads = []

for line in F:
    reads.append(line)

for index,line in enumerate(reads):

    if index == seq_line:
        if line.count("N") > 10:
            bad_reads.append(reads[seq_line-1:seq_line+3])
        else:
            good_reads.append(reads[seq_line-1:seq_line+3])

        seq_line = seq_line + 4 

f_bad = open("wed_bad.fastq","w")
for line in bad_reads:
    for element in line:
        f_bad.write(element)

f_good = open("wed_good.fastq","w")
for line in good_reads:
    for element in line:
        f_good.write(element)

F.close()
f_bad.close()
f_good.close()

```
