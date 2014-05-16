Running programs (from the Beocat head node as well as the queue), Shell scripts
================================================================================

## Code challenge 3

Raw data files from NGS experiments are often very large. To transfer this data faster files are compressed before being downloaded or uploaded. Their are many common forms of file compression. One common form of compression is gzip, `.gz`. The `gunzip` command decompresses gzipped, `.gz`, files.

    USAGE: gunzip [filename ...]

 Today we will use wild cards in our filename and write a loop to unzip, count sequences with `grep`, and `echo` "[Filename] has been decompressed and has [n] sequences" for each fasta file in the `~/pipeline_datasets/NGS` directory.
 
## Code challenge 3 questions:

What was your code:

What was your output:
 
