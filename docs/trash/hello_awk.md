# Hello AWK

!!!- info "Learning outcomes"

    - to run an AWK interpreter
    - to run AWK from the command-line
    - to experience why single quote is most often used
    - to run AWK on an input file

???- question "For teachers"

    Teaching goals are:

    - The learners have run an AWK interpreter
    - The learners have run AWK from the command-line
    - The learners have to experienced why single quote is most often used
    - The learners have run AWK on an input file

    Lesson plan:

    * 5 mins: prior knowledge
    * 5 mins: presentation
    * 15 mins: challenge
    * 5 mins: feedback

## Overview

In this session, we run AWK.

## Exercises

See the exercise procedure [here](../misc/exercise_procedure.md).

### Exercise 1: run an AWK script

!!!- info "Learning outcomes"

    - to run an AWK script

Read:

- [The Wikipedia 'AWK' page, 'Examples'](https://en.wikipedia.org/wiki/AWK#Examples),
  section 'Hello, World!' only

Then do:

- Create a file called `hello_world.awk`, with the 'Hello, world!' example code
- Run the AWK script using `awk -f hello_world.awk`

### Exercise 2: run AWK from the command-line using single quotes

!!!- info "Learning outcomes"

    - to run AWK from the command-line

Creating a script for every AWK use is tedious.
Instead, we will be using AWK one-liners in the terminal:

- run the text of the AWK script as a oneliner, using single-quotes
  around the AWK code, i.e. `awk '[my awk code]'`,
  where `[my awk code]` is your AWK code.

What does the AWK code do?

!!! tip "Use a semicolon to put two statements on one line"

    In this script, the `print` statement
    and the `exit` statement have their own lines. 

    To put these on the same line, 
    use a semicolon (`;`).

???- info "Solution"

    ```
    awk 'BEGIN { print "Hello, world!"; exit }'
    ```

### Exercise 3: run AWK from the command-line using double quotes

!!!- info "Learning outcomes"

    - to experience why single quote is most often used

AWK code is often put between single quotes (`'`), instead of double quotes (`"`).
Here we find out why.

To experience why, do:

- rewrite the answer of the previous exercise to use double quotes.
  There are at least two rewrites possible!

???- info "Solution"

    Here we use an escape character on the internal double quotes:

    ```
    awk "BEGIN { print \"Hello, world!\"; exit }"
    ```

    Here we use single quotes on the internal text:

    ```
    awk "BEGIN { print 'Hello, world!'; exit }"
    ```

Why is the AWK code put between single quotes (`'`), instead of double quotes (`"`)?

Which theoretical event would cause this preference to change to use single quotes?

### Exercise 4: run AWK on an input file

!!!- info "Learning outcomes"

    - to run AWK on an input file

It is common to run AWK on an input file.

- Create an input file called `addr.txt` (it is a file used in the exercises of the book we use)

```title="addr.txt"
Hello World
How are you
This game is good
Today is sunny
12345
You are funny
```

- Run the following command:

```
awk '/is/' addr.txt
```

What does `/is/` do?

## Links

- Book: [CLI text processing with GNU awk](https://learnbyexample.github.io/learn_gnuawk/)
