Using shell scripts, loops and variables to repeat tasks 
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

Your shell script should run using the following command:

```
bash ~/scripts/expand_fasta.sh ~/class/fasta/gzip/*.gz
```
## Code challenge 3 steps:

Write a shell script called `~/scripts/expand_fasta.sh` to:

(1) Take any number of .gz fasta files as input

(2) Make a `for` loop that defines each .gz fasta file as the variable FILE and does the following:
    
    (a) define BASE as the basename of the file (without the .gz extension)
    (b) gunzip the FILE and redirect the output to ~/output with the basename as the file's name
    (c) define COUNT as the number of sequences in the file using the grep command
    (d) print the file's name and number of fasta sequences using echo and your $BASE and $FILE variables


**Tip:** Remember to test your loop by first printing your commands with `echo` rather than executing them
 
## Code challenge 3 questions:

What was your code:

## Code challenge 4

Fasta headers indicate if a paired end read is in the forward or reverse orientation. Older Illumina headers ended in `/1` for forward reads or `/2` for reverse. Illumina changed the read headers to include that information inside of the header rather than at the end.

Most bioinformatics tools did not change their expectation that headers end in `/1` for forward reads or `/2` for reverse. To make sure your tools know which forward read pairs with which reverse read you should reformat your headers if they are for paired end reads and do not end in `/1` or `/2`.

Useful code already exists to do this at http://www.freelists.org/post/mira_talk/Metagenome-assembly,4. 

The conversation explains that you can convert headers using existing bash code after replacing the input filename and output filename with your own:

```
USAGE: cat INPUT.fastq | awk '{if (NR % 4 == 1) {split($1, arr, ":"); printf "%s_%s:%s:%s:%s:%s#0/%s\n", arr[1], arr[3], arr[4], arr[5], arr[6], arr[7], substr($2, 1, 1), $0} else if (NR % 4 == 3){print "+"} else {print $0} }' > OUTPUT.fastq
```

When a sequencing run is done you get many fastq files. I have tested the code above many times and it works to convert new Illumina paired end read headers to the older format that end in `/1` or `/2`.

When creating a new comple filename or string with variables you should braken your variable with curly bracketts (e.g. `~/output/${BASE}_header.fastq`).

Your shell script should run using the following command:

```
bash ~/scripts/convert_headers.sh ~/class/fastq/header/*.fastq
```

##Code challenge 4 steps:

Write a shell script called `~/scripts/convert_headers.sh` to:

(1) Take any number of fastq files as input

(2) Make a for loop that defines each fastq file as the variable FILE and does the following:

    (a) define BASE as the basename of the file (without the .fastq extension)
    (b) use the tested code with FILE as the input and redirect the output to ~/output with the basename plus "_header" as the file's name and .fastq as the extension


## Code challenge 4 questions:

What was your code:
