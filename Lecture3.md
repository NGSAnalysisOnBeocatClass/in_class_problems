Running programs (from the Beocat head node as well as the queue), Shell scripts
================================================================================

## Code challenge 3

Raw data files from NGS experiments are often very large. To transfer this data faster files are compressed before being downloaded or uploaded. Their are many forms of file compression. One common form of compression is gzip, `.gz`. The `gunzip` command decompresses gzipped, `.gz`, files.

    USAGE: gunzip [filename ...]

You can re-direct gunzip output using the `-c` flag and `>`. For example:

```
gunzip -c my.fasta.gz > ~/output/my.fasta
```

You don't have write permissions in the `~/class` directory. You normally want to keep your raw data separate from your working directory and remove write permissions from your raw data directory. We will learn to set permissions next class.

Today we will use wild cards in our fasta filename so that it expands to a list of all gzipped fasta files in the `~/class/fasta/gzip` directory. Wildcards are very useful for describing a list of files with a certain file extension. 

We will also use `basename` to redirect our output to a working directory instead of our raw data directory.
 
Write a shell script called `~/scripts/expand_fasta.sh` to:

(1) Take any number of .gz fasta files as input

(2) Make a `for` loop that defines each .gz fasta file as the variable FILE and does the following:
    
    (a) define BASE as the basename of the file (without the .gz extension)
    (b) gunzip the FILE and redirect the output to `~/output` with the basename as the file's name
    (c) define COUNT as the number of sequences in the file using the `grep` command
    (d) `echo` file's name and number of fasta sequences


**Tip:** Remember to test your loop by first printing your commands with `echo` rather than executing them
 
## Code challenge 3 questions:

What was your code:

 
