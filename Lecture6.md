Arrays and Control loops in Perl in depth 
================================================================================

## Code challenge 7

Using our current skills we can start to see how to write code to customize analysis of text files. 

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

(I) Initilize `$fasta` as the first argument in `@ARGV`.

(II) Initialize variables to hold the count of A's, C's, G's, T's or IUPAC ambiguous bases.

(III) Open `$fasta` as the filehandle `FASTA`. Open the file as "read only".

(IV) Write a while loop to read lines from `FASTA` using the diamond operator.

  (A) Create an `unless` loop within your code block from step IV to skip lines that start with `>`. Within the `unless` loop:

    (1) remove new line characters

    (2) split the sequence at each character using `split` and save all these values as `@seq`
 
    (3) loop through each character with a for loop
    
        (i) within the for loop write five conditional loops in a row testing if the character is an A or a C or a G or a T or an IUPAC ambiguous base (anything else). If the character is one of these increment the counter for that character.
        
(V) close all code blocks

(VI) print how many A's, C's, G's, T's or IUPAC ambiguous bases are in the fasta file

    

