# Working with CSVs

!!!- info "Learning outcomes"

    - use AWK on a CSV

???- question "For teachers"

    Teaching goals are:

    - Learners can use AWK on a CSV

    Lesson plan:

    * 5 mins: prior knowledge
    * 5 mins: presentation
    * 15 mins: challenge
    * 5 mins: feedback

## Overview

In this session, we use AWK on a file with comma-separated values.

## Exercises

See the exercise procedure [here](../misc/exercise_procedure.md).

### Exercise 1: confirming things are true

!!!- info "Learning outcomes"

    - experience the ways to filter on column values of `awk`

#### Download the data

In a terminal, do:

```
wget https://raw.githubusercontent.com/richelbilderbeek/awk_course/master/data/diamonds_raw.csv
```

to download a file called `diamonds_raw.csv`.

#### mix between string and values

In a terminal, in the same folder as where the data is downloaded, do:

```
awk 'NR < 10 { print $1 }' diamonds_raw.csv
```

In English, this is: 'For every line with a line number less than 10,
print the first column's value'.

Confirm that this is true if the columns are separated by a tab.

#### mix between string and values

In a terminal, in the same folder as where the data is downloaded, do:

```
awk -F "," 'NR < 10 { print $1 }' diamonds_raw.csv
```

In English, this is: 'Columns are separated by a comma.
For every line with a line number less than 10,
print the first column's value'.

Confirm that this is true.

#### multi-word strings

In a terminal, in the same folder as where the data is downloaded, do:

```
awk -F "," 'NR < 10 { print $2 }' diamonds_raw.csv
```

In English, this is: 'Columns are separated by a comma.
For every line with a line number less than 10,
print the seconds column's value'.

Confirm that this is true.
