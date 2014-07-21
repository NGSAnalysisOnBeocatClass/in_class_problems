Scalar, lists and arrays and control structures in Perl
=======================================================
## Code challenge 5

## Code challenge 5 questions:
Write a Perl script called `~/scripts/assemble_t.pl` to:

(1) define your forward reads as `$fastq1` and set this value to:

```
/homes/bioinfo/de_novo_transcriptome_2/cell_line_good_1.fastq
```

(2) define your reverse reads as `$fastq2` and set this value to:

```
/homes/bioinfo/de_novo_transcriptome_2/cell_line_good_2.fastq
```

(3) define your output directory as `$assembly_dir` and set this value to:

```
out_put/assemble_t_23
```

(3) write a line of code to print this line using single quotes:

```
export PATH=/homes/bioinfo/bioinfo_software/velvet:/homes/bioinfo/bioinfo_software/oases:${PATH}
```

(4) Write a code to print these lines using double quotes. Have the value of the scalar variable for forward reads replace `FASTQ1` , the value of the variable for reverse reads replace `FASTQ2` and the value of the variable for the assembly directory replace `DIR`:

```
velveth DIR 23 -shortPaired -fastq -separate FASTQ1 FASTQ2 
velvetg DIR -read_trkg yes
oases DIR
```
