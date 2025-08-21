# Variables

!!!- info "Learning outcomes"

    - use a variable

???- question "For teachers"

    Teaching goals are:

    - Learners have practiced using a variable

    Lesson plan:

    - 5 mins: prior knowledge
    - 5 mins: presentation
    - 15 mins: challenge
    - 5 mins: feedback

## Overview

Sometimes we need AWK to remember things,
for example, when summing values

## Exercises

See [the exercise procedure](../misc/exercise_procedure.md).

### Exercise 1: confirming things are true

!!!- info "Learning outcomes"

    - experience variables

#### 1.1. Download the data

In a terminal, do:

```bash
wget https://pmitev.github.io/to-awk-or-not/data/coins.txt
```

to download a file called `coins.txt`.

#### 1.2. Sum

In a terminal, in the same folder as where the data is downloaded, do:

```bash
awk '{ sum = sum + $2 } END { print sum }' coins.txt
```

In English, this is: 'For every line, add the value of the second column
to the variable called `sum`. In the end, print the value of sum.

Confirm that this is true.

#### 1.3. Get the maximum

In a terminal, in the same folder as where the data is downloaded, do:

```bash
awk '$2 > max { max = $2 } END { print max }' coins.txt
```

In English, this is: 'For every line, if the value in the second column
is bigger than the value of `max`, set `max` to the value in the second column.
In the end, print the value of `max`.

Confirm that this is true.

!!! question "What is the assumption about the values in the second column?"

    The assumption about the values in the second column is that zero
    is the lowest possible value, as the initial value of `max` is zero.

    If, for example, all the values in the second column are negative,
    `max` will be zero.

### Exercise 2: explore data

#### 2.1. Download the data

In a terminal, do:

<!-- markdownlint-disable MD013 --><!-- URL cannot be split up over lines, hence will break 80 characters per line -->

```bash
wget https://raw.githubusercontent.com/richelbilderbeek/awk_course/master/data/diamonds_no_header.tsv
```

<!-- markdownlint-enable MD013 -->

to download a file called `diamonds_no_header.tsv`.

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

#### 2.2 Explore the data

Using `awk` only:

- show the number of diamonds in the dataset
- show the number of columns in the dataset
- show the lowest price of all the diamonds
- show the average price of all the diamonds
- show the average price of all the diamonds with an ideal cut
- show the total weight of all diamonds combined in kilos,
  1 carat is 0.0002 kilo
- show the prices of all the diamonds together, in Swedish kroner.
  Assume 1 US dollar is 10.47 Swedish kroner
