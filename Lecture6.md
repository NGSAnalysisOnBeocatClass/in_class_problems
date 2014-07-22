Arrays and Control loops in Perl in depth 
================================================================================

## Code challenge 7

Using our current skills we can start to see how to write code to customize analysis of text files. This ability to quickly write code to ask a specific question about our data is one of Perl's strengths.

We will use conditionals and pattern matching to find find out how many A's, C's, G's, T's or IUPAC ambiguous bases are in a fasta file.

IUPAC ambiguous bases are letter's that indicate that a base mey be one of 2-4 possible bases but there is not enough evidence to decide. N is the most common IUPAC ambiguous base and it indicates that a position may be A,T,C or G. Gaps in sequence assembly that are spanned by mate pairs are often indicated with N's for the estimated length of the gap. For a full list of IUPAC bases see http://www.bioinformatics.org/sms/iupac.html.

Additionally, many assemblers use uppercase and lowercase bases in an assembly. Lowercase bases indicate lower quality portions of the assembly or repeat regions that should be masked. Our script will need to count uppercase and lowercase bases to get an accurate count.

We can use pattern matching in perl similar to the way we used it in grep to find or skip a simple pattern. In Perl if we want to test if `$_` begins with `>` we could write the following code:

```
if (/^>/)
{
  print; # prints only headers
}
```

The `^` here indicates that the character is achored to the start of the line (e.g. it is the first character in the line).

If we want to match another variable in Perl we use the match operator `=~`. So to test if the variable `$na` has the letter A in it I could write:

```
$na =~ /a/i
```

The `i` after the slash indicates I want to match upper or lowercase letters.



## Code challenge 7 questions

Create a Perl script called `~/scripts/count_bases.pl`. Edit this script for your code challenge.

**(1) Initilize `$fasta` as the first argument in `@ARGV`.**

**(2) Initialize variables to hold the count of A's, C's, G's, T's or IUPAC ambiguous bases.**

**(3) Open `$fasta` as the filehandle `FASTA`. Open the file as "read only".**

**(4) Write a while loop to read lines from `FASTA` using the diamond operator.**

(A) Create an `unless` loop within your code block from step 4 to skip lines that start with `>`. Within the `unless` loop:

(i) within the for loop from step A remove new line characters

(ii) also within the for loop from step A split the sequence at each character using `split` and save all these values as `@seq`
 
(iii) also within the for loop from step A loop through each character with a for loop
    
        (a) within the for loop from step iii write five conditional loops in a row testing if the character is an A or a C or a G or a T or an IUPAC ambiguous base (anything else). If the character is one of these increment the counter for that character.
        
(V) close all code blocks

(VI) print how many A's, C's, G's, T's or IUPAC ambiguous bases are in the fasta file

    

