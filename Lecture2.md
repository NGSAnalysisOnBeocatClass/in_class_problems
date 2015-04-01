Files, directories, editing and pipes
=====================================

## Code challenge 1

`/homes/bioinfo/bioinfo_software` is a directory full of bioinformatics tools that can be executed by anyone on Beocat. You can list bioinfo software using an absolute path...

       ls /homes/bioinfo/bioinfo_software

or a relative path (relative to you current working directory or your home directory). Run the `pwd` program to report your current working directory. 

## Code challenge 1 questions:
Write a command with `ls` that uses a relative path and list `bioinfo_software`.

Current working directory:

What was your relative path `ls` command:

## Code challenge 2

FASTA files contain either nucleic acid (DNA or RNA) or amino acid (protein) sequences. Acceptable file extensions for FASTA files are `.fa`, `.fasta`, `.fna` (for nucleic acids) or `.faa` (for amino acids). Read more about FASTA format at http://www.ncbi.nlm.nih.gov/BLAST/blastcgihelp.shtml. 

Each sequence in a FASTA file begins with a header line (">" followed by an optional sequence id). **Note that the optional sequence id or header can use any characters. However the `>` symbol is required in FASTA format.** Sequence data follows and is usually wrapped (making multiple lines).

Here is a simple example of a FASTA file called `test.fasta`.

```
>seq1
ATCGATCGCnTCGGGTACT
TCAGnAAAATGCTCTGATC
TCAG
>seq2
TGCGATCCCTAAGTCATCA
AAATCGCTAGnnTCA
```

The `grep` program searches for patterns within a file. By default it all prints lines with the pattern in the file. **Remember: In "Usage" statements text that is capitalized represents user specified input and optional arguments are bracketed with square brakets ([ ]).**

Here would be typical usage:

   Usage:   grep [OPTIONS] PATTERN [FILE...]

```
$ grep "n" test.fasta
ATCGATCGCnTCGGGTACT
TCAGnAAAATGCTCTGATC
AAATCGCTAGnnTCA
```
The `-c` flag tells `grep` to print the count of lines with the pattern.

```
$ grep -c "n" test.fasta
3
```

## Code challenge 2 questions:
Given what you know about FASTA file format, write a command with `grep` using the `-c` flag that will return the number of sequences in each fasta file in `~/class/fasta`.

**Here again is a simple example of a fasta file called `test.fasta`.**

```
>my_header1
ATCGATCGCnTCGGGTACT
TCAGnAAAATGCTCTGATC
TCAG
>my_header2
TGCGATCCCTAAGTCATCA
AAATCGCTAGnnTCA
```

Number of sequences in each FASTA file:

What was your `grep` command:
