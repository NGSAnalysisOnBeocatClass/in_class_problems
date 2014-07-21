Arrays and Control loops in Perl in depth 
================================================================================

## Code challenge 7

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

(1) Initilize `$fasta` as the first argument in `@ARGV`.

(2) Open `$fasta` as the filehandle `FASTA`. Open the file as "read only".

(3) Write a while loop to read lines from `FASTA` using the diamond operator.

(4) Create an `unless` loop within your code block from step 3 to skip lines that start with `>`.

(5) With in the `unless` loop:

 (a) remove new line characters

 (b) split the sequence at each character using `split` and save these values as `@seq`
 
 (c)

