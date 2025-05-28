# BEGIN and END

!!!- info "Learning outcomes"

    - be able to do something at the start of an AWK script
    - be able to do something at the end of an AWK script

???- question "For teachers"

    Teaching goals are:

    - Learners are able to do something at the start of an AWK script
    - Learners are able to do something at the end of an AWK script

    Lesson plan:

    - 5 mins: prior knowledge
    - 5 mins: presentation
    - 15 mins: challenge
    - 5 mins: feedback

## Overview

Sometimes one needs to do things before the actual calculation starts.
Also, sometimes one needs to do things after the actual calculation has run.

Here we do things at the start and end of an AWK script.

## Exercises

See the exercise procedure [here](../misc/exercise_procedure.md).

### Exercise 1: confirming things are true

!!!- info "Learning outcomes"

    - experience the `BEGIN` and `END` blocks

#### Download the data

In a terminal, do:


```bash
wget https://pmitev.github.io/to-awk-or-not/data/coins.txt
```

to download a file called `coins.txt`.

#### `BEGIN`

In a terminal, in the same folder as where the data is downloaded, do:

```bash
awk 'BEGIN {print "There I go!" }' coins.txt
```

In English, this is: 'At the start, print 'There I go!''.

Confirm that this is true.

#### `BEGIN` and a print

In a terminal, in the same folder as where the data is downloaded, do:

```bash
awk 'BEGIN {print "Coin minting years:" } { print $3 }' coins.txt
```

In English, this is: 'At the start, print 'Coin minting years:',
then, for every line, print the third column.

Confirm that this is true.

#### `END`

In a terminal, in the same folder as where the data is downloaded, do:

```bash
awk 'END {print "Done!" }' coins.txt
```

In English, this is: 'In the end, print 'Done!''.

Confirm that this is true.

#### `END` and a `print`

In a terminal, in the same folder as where the data is downloaded, do:

```bash
awk '{ print $0 } END { print "Done!" }' coins.txt
```

In English, this is: 'For every line, print the line.
In the end, print 'Done!''.

Confirm that this is true.

#### `BEGIN` and `END` and a `print`

In a terminal, in the same folder as where the data is downloaded, do:

```bash
awk 'BEGIN { print "Start!" } { print $0 } END { print "Done!" }' coins.txt
```

In English, this is: 'At the start, print 'Start!'.
Then, for every line, print the line. In the end, print 'Done!''.

Confirm that this is true.

#### `BEGIN` and `END` and a condition and a `print`

In a terminal, in the same folder as where the data is downloaded, do:

```bash
awk 'BEGIN { print "Start!" } $1 == "gold" { print $0 } END { print "Done!" }' coins.txt
```

In English, this is: 'At the start, print 'Start!'. Then, for every line,
if the first column matches `gold`, print the line. In the end, print 'Done!''.

Confirm that this is true.

### Exercise 2: explore data

!!!- info "Learning outcomes"

    - practice using the `BEGIN` and `END` blocks

#### Download the data

In a terminal, do:

<!-- markdownlint-disable MD013 --><!-- URL cannot be split up over lines, hence will break 80 characters per line -->

```bash
wget https://raw.githubusercontent.com/richelbilderbeek/awk_course/master/data/diamonds.tsv
```

<!-- markdownlint-enable MD013 -->

to download a file called `diamonds.tsv`.

This file is a tab-separated file about diamonds and
is part of the `ggplot2` R package.

- [Raw data](https://raw.githubusercontent.com/tidyverse/ggplot2/main/data-raw/diamonds.csv)
- [Data description](https://ggplot2.tidyverse.org/reference/diamonds.html)

The dataset has the following columns:

<!-- markdownlint-disable MD013 --><!-- Tables cannot be split up over lines, hence will break 80 characters per line -->

index|name   |description
-----|-------|------------------------------------------------------------------
1    |carat  |weight of the diamond (0.2--5.01)
2    |cut    |quality of the cut (Fair, Good, Very Good, Premium, Ideal)
3    |color  |diamond colour, from D (best) to J (worst)
4    |clarity|a measurement of how clear the diamond is (I1 (worst), SI2, SI1, VS2, VS1, VVS2, VVS1, IF (best))
5    |depth  |total depth percentage = z / mean(x, y) = 2 * z / (x + y) (43--79)
6    |table  |width of top of diamond relative to widest point (43--95)
7    |price  |price in US dollars ($326--$18,823)
8    |x      |length in mm (0--10.74)
9    |y      |width in mm (0--58.9)
10   |z      |depth in mm (0--31.8)

<!-- markdownlint-enable MD013 -->

#### Explore the data

Using `awk` only:

- show a text 'Number of lines:', then print the number of lines
- show a text 'Number of columns:', then print the number of columns
- show a text 'Header:', then print only the header
- show a text 'Prices of first five diamonds:',
  then print the prices of the first five diamonds, while skipping the header
- show the line number of the diamonds that have a price below $400 USD,
  while skipping the header.
  At the end, print "... those were he cheapest diamonds"
- show a text 'Prices (in USD) of diamonds with a fair and worst color:'.
  Then show the price of the diamonds that have a fair cut and the worst color,
  while skipping the header.
  Then show the text 'Done!'

Think:

- these practice questions are only about printing.
  Could you already guess where `BEGIN` and `END`
  become more useful?
