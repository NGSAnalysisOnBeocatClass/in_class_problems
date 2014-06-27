Files, directories, editing and pipes
=====================================

## Code challenge 1

`/homes/bioinfo/bioinfo_software` is a directory full of bioinformatics tools that can be executed by anyone on Beocat. You can list bioinfo software using an absolute path:

       ls /homes/bioinfo/bioinfo_software

Or a relative path (relative to you current working directory or your home directory). Run the pwd command and report your current directory. 

## Code challenge 1 questions:
Write a command with `ls` that uses a relative path and list `bioinfo_software`.

Current working directory:

What was your relative path `ls` command:

## Code challenge 2

Each sequence in a fasta file begins with a header line (">" followed by a sequence id). Sequence data follows and is usually wrapped (making multiple lines).

Here is a simple example of a fasta file called test.fasta.

```
>seq1
ATCGATCGCnTCGGGTACT
TCAGnAAAATGCTCTGATC
TCAG
>seq2
TGCGATCCCTAAGTCATCA
AAATCGCTAGnnTCA
```

The `grep` program searches for patterns within a file. By default it all prints lines with the pattern in the file. ** Remember: In "Usage" statements text that is capitalized, bracketed with square brakets ([ ]) or diamond brakets (< >) represents user specified input.**

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
4
```

## Code challenge 2 questions:
Given what you know about fasta file format, write a command with `grep` using the `-c` flag that will return the number of sequences in each fasta file in `~/class/fasta`.

Number of sequences in each file:

What was your `grep` command:
