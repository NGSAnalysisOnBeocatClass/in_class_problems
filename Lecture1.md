Files, directories, editing and pipes
=====================================

## Code challenge 1

`/homes/bioinfo/bioinfo_software` is a directory full of bioinformatics tools that can be executed by anyone on Beocat. You can list bioinfo software using an absolute path:

       ls /homes/bioinfo/bioinfo_software

Or a relative path (relative to you current working directory or your home directory). Run the pwd command and report your current directory. Write a `ls` command that uses a relative path and list `bioinfo_software`.

## Code challenge 1 question:

Current working directory:

What was your relative path `ls` command:

## Code challenge 2

Durring class we learned about SAM sequence alignment format files and BAM the binary version of the same thing. Samtools is a popular bioinformatics package with many commands that manipulate SAM and BAM files.

Many samtools commands are tailored to work with SAM/BAM format files but they work like Unix commands (e.g. they can be joined using `|` to avoid printing uneeded intermediate files) and to speed up small jobs. When creating a workflow for samtools use `-` in place of input or output files. It is better not to use pipes on extremely large Bam or Sam files. Text that is captioned with square brakets ([]) or diamond brakets (<>) represents user specified input.

Here would be typical usage:

       Usage:   samtools <command> [options]
       
Here would be typical piped usage:

       Usage:   samtools <command> [options] [input] - | samtools <command> [options] - - | samtools <command> [options] - [output]

However, pipes depend on the program reading in from standard in and sending output to standard out by default. A few samtools have a different default behavior. Because of this a couple samtools commands should be treated differently.

**samtools view**

`view` outputs to standard out by default so you should exclude the `-` to indicate output file.

       Usage at begining of pipe:   samtools view [options] [input] |
       
       Usage in middle of pipe:   | samtools view [options] - |
       
       
**samtools sort**

Without the -o parameter nothing is output to standard out. This means the next step in the piped workflow gets no input. The `-o` parameter for `sort` indicates that samtools should "Output the final alignment to the standard output".

       Usage at begining of pipe:   samtools sort [options] [input] -o - |
       
       Usage in middle of pipe:   | samtools sort [options] -o - - |

Write a command with pipe to compress your sam file to bam, sort it, remove PCR duplicates, and report simple statistics on the de-duplicated bam.

Run samtools without any arguments to see which commands to use:

       /homes/bioinfo/bioinfo_software/samtools/samtools 
       
Run samtools with a command but no arguments to see a detailed help menu for individual commands or read a detailed manual at http://samtools.sourceforge.net/samtools.shtml#3. 

Below I have added the `S` option (aka parameter) to the `samtools view` command. The `S` parameter indicates "input is in SAM." I have also added the `u` option to the `samtools view` command which specifies "output in the uncompressed BAM format". I would have used the `b` for "output in BAM format in place of `u` if I was not piping my workflow. Using pipes and `u` speeds up the workflow below.

```
/homes/bioinfo/bioinfo_software/samtools/samtools view -Su [test.sam] -o [test.bam] 

/homes/bioinfo/bioinfo_software/samtools/samtools sort [test.bam] [test_sort]

/homes/bioinfo/bioinfo_software/samtools/samtools rmdup [test_sort.bam] [test_rmdup.bam]

/homes/bioinfo/bioinfo_software/samtools/samtools flagstat [test_rmdup.bam]
```
## Code challenge 2 question:

Pipe these four commands together and report some values from the flagstat summary.

Percent of reads that mapped: 

Percent of reads the were properly paired: 

What was your piped command: 
