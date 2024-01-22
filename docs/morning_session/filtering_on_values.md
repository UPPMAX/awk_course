# Filtering on values

!!!- info "Learning objectives"

    - filter based on column values

???- question "For teachers"

    Teaching goals are:

    - Learners can filter based on column values

    Lesson plan:

    * 5 mins: prior knowledge
    * 5 mins: presentation
    * 15 mins: challenge
    * 5 mins: feedback

## Overview

AWK is great for selecting elements of tabular data.

In this session, we use AWK to select elements in tabular data.
Selecting elements, in this case, is also called 'filtering'.

## Exercises

See the exercise procedure [here](../misc/exercise_procedure.md).

### Exercise 1: confirming things are true

!!!- info "Learning objectives"

    - experience the ways to filter on column values of `awk`

#### Download the data

In a terminal, do:

```
wget https://pmitev.github.io/to-awk-or-not/data/coins.txt
```

to download a file called `coins.txt`.

#### match on equality

In a terminal, in the same folder as where the data is downloaded, do:

```
awk '$1 == "gold" { print }' coins.txt
```

In English, this is: 'For every line where the first column matches `gold`, 
show the whole line'.

Confirm that this is true.

#### use less-then operator

In a terminal, in the same folder as where the data is downloaded, do:

```
awk '$2 < 1.0 { print }' coins.txt
```

In English, this is: 'For every line where the second column is less than one, 
show the whole line'

Confirm that this is true.

#### show the first line

In a terminal, in the same folder as where the data is downloaded, do:

```
awk 'NR == 1 { print }' coins.txt
```

In English, this is: 'If the line number is one, print the line'

Confirm that this is true.

#### skip a first line

In a terminal, in the same folder as where the data is downloaded, do:

```
awk 'NR > 1 { print }' coins.txt
```

In English, this is: 'If the line number is bigger than one, print the line'

Confirm that this is true.

#### use `&&` operator

In a terminal, in the same folder as where the data is downloaded, do:

```
awk '$1 == "gold" && $2 < 1.0 { print }' coins.txt
```

In English, this is: 'For every line where the first column matches `gold`
**and** the value in the second column is less than 1.0, show the whole line'

Confirm that this is true.

#### use `||` operator

In a terminal, in the same folder as where the data is downloaded, do:

```
awk '$1 == "gold" || $2 < 1.0 { print }' coins.txt
```

In English, this is: 'For every line where the first column matches `gold`
**or** the value in the second column is less than 1.0, show the whole line'

Confirm that this is true.

#### multiple conditions

In a terminal, in the same folder as where the data is downloaded, do:

```
awk '$1 == "gold" { print "Gold:", $0 } $2 < 1.0  { print "Light:" $0 }' coins.txt
```

In English, this is: 'For every line where the first column matches `gold`,
print 'Gold:' and the line. 
For every line where the second column is less than 1.0,
print 'Light:' and the line. 

Confirm that this is true.

### Exercise 2: printing

#### Download the data

In a terminal, do:

```
wget https://raw.githubusercontent.com/richelbilderbeek/awk_course/master/data/diamonds_no_header.tsv
```

to download a file called `diamonds_no_header.tsv`.

This file is a tab-separated file about diamonds and 
is part of the `ggplot2` R package.

 * [Raw data](https://raw.githubusercontent.com/tidyverse/ggplot2/main/data-raw/diamonds.csv)
 * [Data description](https://ggplot2.tidyverse.org/reference/diamonds.html)

The dataset has the following columns:

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

#### Explore the data

Using `awk` only:

- show the cut of the diamonds that have a price above $18000 USD
- show the price of the diamonds that have a fair cut and the worst color
- show the line number of the diamonds that have a price below $400 USD

### Exercise 3: printing a complete dataset

#### Download the data

In a terminal, do:

```
wget https://raw.githubusercontent.com/richelbilderbeek/awk_course/master/data/diamonds.tsv
```

to download a file called `diamonds.tsv`.

It is the same dataset as used earlier.
However, it has a first line, which is called a header,
which describes the data. 

#### Explore the data

Using `awk` only:

- show the number of lines (in a smart way)
- show the number of columns (in a smart way)
- show only the first line
- show only the first ten lines
- show the prices of all diamonds, while skipping the header
- show the cut of the diamonds that have a price above $18000 USD, while skipping the header
- show the price of the diamonds that have a fair cut and the worst color, while skipping the header
- show the line number of the diamonds that have a price below $400 USD, while skipping the header

Explain:

- although this dataset has a header, in not all exercises `NR > 1` was needed.
  When can `NR > 1` be omitted safely?
