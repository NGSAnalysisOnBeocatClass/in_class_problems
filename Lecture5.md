Scalar, lists and arrays and control structures in Perl
=======================================================
## Code challenge 5

Popular bioinformatics tools often have separate programs that you call to complete your analysis. They also have their own usage statments and rules for passing your input arguments to them. It is a good idea to write a script to properly format these commands so that you do not introduce errors the next time you run the program.

When assembling Illumina fastq reads you should use a de Bruijn graph assembler. When assembling transcriptomes from Illumina fastq reads you should use a de Bruijn graph assembler that has been modified specfically for transcriptomes.

We will be writting commands for velvet (a de Bruijn graph genome assembler) and oases (a program developed to take initial output of velvet and run a transcriptome assembly). You can read a detailed list of parameter options for Oases transcriptome assembler by visiting the Oases manual at https://www.ebi.ac.uk/~zerbino/oases/.

You can print help menus for the three programs in the commands below by typing:

```
/homes/bioinfo/bioinfo_software/velvet/velveth
/homes/bioinfo/bioinfo_software/velvet/velvetg
/homes/bioinfo/bioinfo_software/oases/oases
```

We will use the `say` command in Perl to print our single or double quoted strings with newline characters automatically so we should add the following to our script before `use strict`:

```
use 5.010;
```

Now our script should start with :

```
#!/usr/bin/perl
# USAGE:
# DESCRIPTION:
use 5.010; # this script requires Perl 5.10 or greater
use strict;
use warnings;
```

## Code challenge 5 questions:
Create a Perl script called `~/scripts/assemble_t.pl` to:

(1) define your forward reads as `$fastq1` and set this value to:

```
'~/class/cell_line_good_1.fastq'
```

(2) define your reverse reads as `$fastq2` and set this value to:

```
'~/class/cell_line_good_2.fastq'
```

(3) define your output directory as `$assembly_dir` and set this value to:

```
'out_put/assemble_t_23'
```

(4) write a line of code to print this line using single quotes:

```
export PATH=/homes/bioinfo/bioinfo_software/velvet:/homes/bioinfo/bioinfo_software/oases:${PATH}
```

(5) Write a code to print these lines using double quotes. Have the value of the scalar variable for forward reads replace `FASTQ1` , the value of the variable for reverse reads replace `FASTQ2` and the value of the variable for the assembly directory replace `DIR`:

```
velveth DIR 23 -shortPaired -fastq -separate FASTQ1 FASTQ2 
velvetg DIR -read_trkg yes
oases DIR
```

(6) make your script executable using `chmod 755`.

## Code challenge 6

## Code challenge 6 questions:

Make a copy or your Perl script called `~/scripts/assemble_t.pl` and name this copy `~/scripts/kmer_assemble_t.pl` using the `cp` Bash command. **Edit your `~/scripts/kmer_assemble_t.pl` script for this code challenge.**

(1) Redefine your output directory as `$assembly_dir` and set this value to:

```
'out_put/assemble_t'
```

(2) Put your code from step 5 in code challenge 5 into a for loop now that iterates through all **odd values from 25 to 39**. We will use a special kind of for loop to go from a minimum value to a maximum value incrementing by some number each time. 

Below is an example of a for loop that prints the values from 1 to 100 by increments of 10

```
for ( my $k = 0; $k <= 100; $k += 10)
{
    say $k;
}
```

(3) Change the inside of the code block you just created to replace the letter `K` with your variable for k. Remember to put your variables in curly braces when printing them without white spaces surrounding them. All other variables can be used in the same way you did in code challenge 5.

```
velveth DIR_K K -shortPaired -fastq -separate FASTQ1 FASTQ2 
velvetg DIR_K -read_trkg yes
oases DIR_K
```

(4) make your script executable using `chmod 755`.

