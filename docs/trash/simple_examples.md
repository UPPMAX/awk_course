# Simple examples

!!!- info "Learning outcomes"

    - .

???- question "For teachers"

    Teaching goals are:

    - .

    Other goals are:

    - .

    Lesson plan:

    * 5 mins: prior knowledge
    * 5 mins: presentation
    * 15 mins: challenge
    * 5 mins: feedback

## Overview

In this session, we learn about AWK.

## Exercises

See the exercise procedure [here](../misc/exercise_procedure.md).

### Exercise 1: Simple examples 1

!!!- info "Learning outcomes"

    - Use `awk` for the first time
    - Do a simple match
    - Use the caret as a matcher

Start at the top of ['To Awk Or Not'](https://pmitev.github.io/to-awk-or-not/) 
of the page '1. Simple examples', until the first question.

Make sure to run the first example: `awk '/gold/' coins.txt`, 
to ensure you can actually use `awk`.

???- question "I get an error, how do I fix it?"

    This error proves that `awk` is not installed:

    ```
    $ awk '/gold/' coins.txt
    awk: command not found
    ```

    Solution: install `awk`.

    This error shows that the file `coins.txt` is not found:

    ```
    $ awk '/gold/' coins.txt
    awk: fatal: cannot open file `coins.txt' for reading: No such file or directory
    ```

    Solution: download the file from <https://pmitev.github.io/to-awk-or-not/data/coins.txt>,
    for example, by doing:

    ```
    wget https://pmitev.github.io/to-awk-or-not/data/coins.txt
    ```

> Try to run the above example for "silver". What is different? How can one fix it?

Answer the question.

???- info "Solution"

    ```
    $ awk '/silver/' coins.txt
    silver  10    1981  USA                 ingot
    gold     0.1  1986  PRC                 Panda - silver lined
    silver   1    1986  USA                 Liberty dollar
    silver   0.5  1986  USA                 Liberty 50-cent piece
    silver   1    1987  USA                 Constitution dollar
    ```

    ```
    $ awk '/^silver/' coins.txt
    silver  10    1981  USA                 ingot
    silver   1    1986  USA                 Liberty dollar
    silver   0.5  1986  USA                 Liberty 50-cent piece
    silver   1    1987  USA                 Constitution dollar
    ```

### Exercise 1: Simple examples 2

!!!- info "Learning outcomes"

    - Use the `awk` `&&` operator
    - Maybe use a Linux pipe
    - First example of multiple solutions

Continue reading until the next question:

> Can you find all "silver" coins older than 1986? 
> One can use grep to filter the silver coins and pipe the result to awk 
> or do it all together in awk.

Answer the question.

???- info "Solution"

    Using the 'and' operator:

    ```
    $ awk '$1 == "silver" && $3 < 1986' coins.txt
    silver  10    1981  USA                 ingot
    ```

    Using a Linux pipe:

    ```
    $ awk '/^silver/' coins.txt | awk '$3 < 1986'
    silver  10    1981  USA                 ingot
    ```

### Exercise 1: Simple examples 3

!!!- info "Learning outcomes"

    - Use the `awk` `!` operator

> Unfortunately, awk does not have a way to print/address all fields after or before a selected one. 
> How can one print all remaining fields?

???- info "Solution"

    By negating the condition:

    ```
    $ awk  '!($1 == "silver" && $3 < 1986)' coins.txt
    gold     1    1986  USA                 American Eagle
    gold     1    1908  Austria-Hungary     Franz Josef 100 Korona
    gold     1    1984  Switzerland         ingot
    gold     1    1979  RSA                 Krugerrand
    gold     0.5  1981  RSA                 Krugerrand
    gold     0.1  1986  PRC                 Panda - silver lined
    silver   1    1986  USA                 Liberty dollar
    gold     0.25 1986  USA                 Liberty 5-dollar piece
    silver   0.5  1986  USA                 Liberty 50-cent piece
    silver   1    1987  USA                 Constitution dollar
    gold     0.25 1987  USA                 Constitution 5-dollar piece
    gold     1    1988  Canada              Maple Leaf
    ```

### Exercise 1: Simple examples 4

!!!- info "Learning outcomes"

    - Rehearse that `awk` works on tab-separated values

> A tab separated version 'coins.tab' is more appropriate in such cases 
> and rather common, for the same reason, 
> in many bioinformatics file formats `gff`|`bed`|`sam`|`vcf`.

Do you agree?

???- info "Solution"

    Indeed, AWK works on tab-separated files, commonly having the `tsv`
    extension, where `tsv` is short for 
    [Tab-separated values](https://en.wikipedia.org/wiki/Tab-separated_values).

## Links

 * [Book 'CLI text processing with GNU awk'](https://learnbyexample.github.io/learn_gnuawk/)
