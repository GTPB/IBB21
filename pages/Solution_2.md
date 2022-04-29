
## Solution for Exercise 2

```python
#!/usr/bin/env python3

#opening fastq file
with open("SRR_test.fastq","r") as f:

    # sequence index
    seq_line = 1
    # generators for good and bad reads
    good_reads = []
    bad_reads = []


    x = f.readlines() # puts all lines in a list. Each line is an element in the list

    for index, line in enumerate(x):
        if index == seq_line: 
            
            if line.count("N") > 10:
                bad_reads.append(x[seq_line-1:seq_line+3])

            else:
                good_reads.append(x[seq_line-1:seq_line+3])

            seq_line = seq_line + 4

# writing bad reads file
with open ("bad_reads.fastq","w") as f3:
    for line in bad_reads:
        for element in line:
            f3.write(element)

# writing good reads file
with open("good_reads.fastq","w") as f2:
    for line in good_reads:
        for element in line:
            f2.write(element)
```
