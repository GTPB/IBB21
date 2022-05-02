#!/usr/bin/env python3

FASTA=open("2.fa","r")

FASTA_Dict = {}
FASTA_header = ""


for line in FASTA:
	if ">" in line:
		FASTA_header = line
		FASTA_Dict[FASTA_header] = ""
	else:
		FASTA_Dict[FASTA_header] += line

print(FASTA_Dict)

for sequence in FASTA_Dict.values():
	Perc_GC_Content = (sequence.count("G") + sequence.count("C")) /len(sequence) * 100

	print(Perc_GC_Content)

