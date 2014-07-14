Running programs (from the Beocat head node as well as the queue), Shell scripts
================================================================================

## Code challenge 3

Raw data files from NGS experiments are often very large. To transfer this data faster files are compressed before being downloaded or uploaded. Their are many forms of file compression. One common form of compression is gzip, `.gz`. The `gunzip` command decompresses gzipped, `.gz`, files.

    USAGE: gunzip [filename ...]

Today we will use wild cards in our fasta filename so that it expands to a list of all fasta files in the `~/class/fasta/gzip` directory. Wildcards are very useful for describing a list of files with a certain file extension. 
 
Write a loop to:

(1) unzip 

(2) count number of sequences with `grep`

(3) `echo` file's name and number of fasta sequences

Do this for each fasta file in the `~/class/fasta/gzip` directory.

**Tip:** Remember to test your loop by first printing your commands with `echo` rather than executing them
 
## Code challenge 3 questions:

What was your code:

What was your output:
 
