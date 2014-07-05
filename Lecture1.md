Introduction to commandline
===========================

## Code challenge 0

# Sample

Below is a sample of a usage statement and then a command followed by the parts of the command. This command copies a file from a source location to a directory (in this case the ~/ is your home directory). The option indicates that the user will be interactively prompted before overwriting an existing file.

```
  USAGE: cp [OPTION]... SOURCE... DIRECTORY
```
  
Command:

```

  cp -i /homes/bioinfo/pipeline_datasets/sam_bam/adrenal_rep_1_tophat2_out_1/deletions.bed ~/
  
```
  
Sample program: cp

Sample option or options: -i

Sample source: /homes/bioinfo/pipeline_datasets/sam_bam/adrenal_rep_1_tophat2_out_1/deletions.bed

Sample destination: ~/

# Example 1

Below are examples of usage statements and then examples of commands. 

```
  USAGE: ls [OPTION]... [FILE OR PATH]...
  
```

Command:

```
  ls -l /homes/bioinfo/bioinfo_software
  
```
  
## Code challenge 0a questions

Dissect the commands and report:


Example 1 option or options (flags):

Example 1 file or path:

Example 1 program:

##Code challenge 0b

When reading a github markdown page you will see code boxes like the one below:

```
This is a code box
```
In a code box lines of text preceeded by a `#` are comments. Comments are notes to the user that are skipped by the shell. 

```
#this line is a comment
```

If a line is longer than the screen you must scroll the code box to the right to read the end of the line. Code boxes work this way to avoid wrapping text. Everytime you hit enter in a commandline session your command is sent to the shell for evaluation. Wrapped text can introduce extra end-of-line characters and make it seem to the shell that you entered multiple brocken commands.

Try reading the word "finish" at the end of the line below:

```
cd /directory/directory/directory/directory/directory/directory/directory/directory/directory/directory/directory/directory/directory/directory/directory/directory/directory/directory/directory/directory/directory/finish
```

If you can't than your browser can display this file as a plain text file so that you can read the entire file. Press the "raw" button at the top of this page to view the raw text. Code boxes will start and finish with three back quotes.

## Code challenge 0b questions

What is the last word in the following code box?


```
cp /directory/directory/directory/directory/directory/directory/directory/directory/directory/directory/directory/directory/directory/directory/directory/directory/directory/directory/directory/directory/directory/finish/test.txt answer.txt
```


