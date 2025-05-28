# AWK as a filter

!!!- info "Learning outcomes"

    - Use AWK as a filter
    - Learn the regex metacharacter for 'Matches the starting position within the string'

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

AWK is used as a filter, i.e. a program that can select part
of a text (including none or all).

Here we use AWK to select lines that follow a simple regular expression.

## Exercises

### Exercise 1: a filter

!!!- info "Learning outcomes"

    * Use a filter

Read of [CLI text processing with GNU awk](https://learnbyexample.github.io/learn_gnuawk/):

- chapter '3. Awk introduction', section 'Filtering'

Answer these questions of that same chapter:

- 1

### Exercise 2: a filter with a metacharacter

!!!- info "Learning outcomes"

    - Rehearse using AWK as a filter
    - Learn the regex metacharacter for 'Matches the starting position within the string'

Read of [To awk or not](https://pmitev.github.io/to-awk-or-not):

- chapter '1.Simple examples', section 'Let's begin simple', until the first exercise

Then do:

- the first part of the exercise on that page: `Try to run the above example for "silver". What is different?`

The second question 'How to fix it?' can be answered in two ways,
depending on your current knowledge:

- phrase, in English, how to fix this
- change to AWK code to do what you want

First, in English, how to fix this?

???- info "Solution"

    In English, the answer to 'How to fix this?' is:

    We must select only the lines that *start with* `silver`

To change the AWK code to do what we want,
one needs to know the regular expression to express that.

To find the regular expression metacharacter:

- Browse to <https://www.regextester.com/>
- At the right-hand side, in the panel with 'Top regular expressions',
  scroll down to find the metacharacter we need
- Change to AWK code to do what you want

???- info "Solution"

    To select only the lines that start with `silver`,
    one needs to know that there is a regular expression
    for 'a line that starts with', which is the caret, `^`.

    This means that `^silver` is the regular expression
    for 'all lines that start with the text `silver`.

    Hence, this gives us what we want:

    `awk '/^silver/' coins.txt
