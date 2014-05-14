Files, directories, editing and pipes
=====================================

## Code challenge 1

You can list bioinfo software using an absolute path:

       ls /homes/bioinfo/bioinfo_software

Or a relative path (relative to you current working directory or your home directory). Run the pwd command and report your current directory. Write a `ls` command that uses a relative path and list `bioinfo_software`.

Current working directory:

Relative path `ls` command:

## Code challenge 2

Many samtools commands are tailored to work with SAM/BAM format files but they work like Unix commands (e.g. they can be joined using `|` to avoid printing uneeded intermediate files) and to speed up small jobs. When creating a workflow for samtools use `-` in place of input or output files. It is better not to use pipes on extremely large Bam or Sam files.

Here would be typical usage:

       Usage:   samtools <command> [options]
       
Here would be typical piped usage:

       Usage:   samtools <command> [options] [input] - | samtools <command> [options] - - | samtools <command> [options] - [output]

However, pipes depend on the program reading in from standard in and sending output to standard out by default. Because of this a couple samtools commands should be treated differently.

**samtools view**

`view` outputs to standard out by default so you should exclude the `-` to indicate output file.

       Usage at begining of pipe:   samtools view [options] [input] |
       
       Usage in middle of pipe:   | samtools view [options] - |
       
       
**samtools sort**

Without the -o parameter nothing is output to standard out. This means the next step in the piped workflow gets no input. The `-o` parameter for `sort` is indicates that samtools should "Output the final alignment to the standard output".

       Usage at begining of pipe:   samtools sort [options] [input] -o - |
       
       Usage in middle of pipe:   | samtools sort [options] -o - - |

Write a command with pipe to compress your sam file to bam, sort it, remove PCR duplicates, and report simple statistics on the de-duplicated bam.

Run samtools without any arguments to see which commands to use:

       /homes/bioinfo/bioinfo_software/samtools/samtools 
       
Run samtools with a command but no arguments to see a detailed help menu for individual commands or read a detailed manual at http://samtools.sourceforge.net/samtools.shtml#3.
       
/homes/bioinfo/bioinfo_software/samtools/samtools view -Sb test.sam -o test.bam 

/homes/bioinfo/bioinfo_software/samtools/samtools sort test.bam test_sort

/homes/bioinfo/bioinfo_software/samtools/samtools rmdup test_sort.bam test_rmdup.bam

/homes/bioinfo/bioinfo_software/samtools/samtools flagstat test_rmdup.bam


Pipe these four commands together and report the flagstat summary.

Flagstat summary:


