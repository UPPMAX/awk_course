# print

!!!- info "Learning objectives"

    - print a line
    - print a column of a line
    - print the line number
    - print the number of columns
    - print a multiplied value

???- question "For teachers"

    Teaching goals are:

    - Learners can print a line
    - Learners can print a column of a line
    - Learners can print the line number
    - Learners can print the number of columns
    - Learners can print a multiplied value

    Lesson plan:

    * 5 mins: prior knowledge
    * 5 mins: presentation
    * 15 mins: challenge
    * 5 mins: feedback

## Overview

AWK is great for printing parts of tabular data.

In this session, we use AWK to print.

## Exercises

See the exercise procedure [here](exercise_procedure.md).

### Exercise 1: confirming things are true

!!!- info "Learning objectives"

    - experience the many printing statements of `awk`

#### Download the data

In a terminal, do:

```
wget https://pmitev.github.io/to-awk-or-not/data/coins.txt
```

to download a file called `coins.txt`.

This file is a tab-separated file, with the following columns:

index|description
-----|-----------------
1    |metal
2    |weight in ounces
3    |data minted
4    |country of origin
5    |description

#### `print`

In a terminal, in the same folder as where the data is downloaded, do:

```
awk '{ print }' coins.txt
```

In English, this is: 'For every line, print the whole line'.

Confirm that this is true.

#### `print` and `$0`

In a terminal, in the same folder as where the data is downloaded, do:

```
awk '{ print $0 }' coins.txt
```

In English, this is: 'For every line, print the whole line'.

Confirm that this is true.

#### `$1`

In a terminal, in the same folder as where the data is downloaded, do:

```
awk '{ print $1 }' coins.txt
```

In English, this is: 'For every line, print the first column'.

Confirm that this is true.

#### Multiple columns

In a terminal, in the same folder as where the data is downloaded, do:

```
awk '{ print $1 $2 }' coins.txt
```

In English, this is: 'For every line, print the first column and second column'.

Confirm that this is true.

#### Multiple columns seperated by a space

In a terminal, in the same folder as where the data is downloaded, do:

```
awk '{ print $1, $2 }' coins.txt
```

In English, this is: 'For every line, print the first column and second column,
separated by a space'.

Confirm that this is true.

#### `NF`

In a terminal, in the same folder as where the data is downloaded, do:

```
awk '{ print NF }' coins.txt
```

In English, this is: 'For every line, print the number of columns'.

Confirm that this is true.

#### `$NF`

In a terminal, in the same folder as where the data is downloaded, do:

```
awk '{ print $NF }' coins.txt
```

In English, this is: 'For every line, print the last column'.

Confirm that this is true.

#### `NR`

In a terminal, in the same folder as where the data is downloaded, do:

```
awk '{ print NR }' coins.txt
```

In English, this is: 'For every line, print that line's number'.

Confirm that this is true.

#### Convert

The second column shows the weight in ounces.
One ounce is 28.349523125 gram.

In a terminal, in the same folder as where the data is downloaded, do:

```
awk '{ print $2 * 28.349523125 }' coins.txt

```

In English, this is: 'For every line, show the second column multiplied by 28.349523125'.

Confirm that this is true.

#### Add text

The second column shows the weight in ounces.
One ounce is 28.349523125 gram.

In a terminal, in the same folder as where the data is downloaded, do:

```
awk '{ print $2 * 28.349523125, "gram" }' coins.txt
```

In English, this is: 'For every line, 
show the second column multiplied by 28.349523125 
and add the word 'gram' (separated by a whitespace)'.

Confirm that this is true.

### Exercise 2: explore data

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

- show the number of diamonds in the dataset (in any clumsy way!)
- show the number of columns in the dataset (in any clumsy way!)
- show the prices of the diamonds in US dollars
- show the prices of the diamonds in Swedish kroner, 
  assume 1 US dollar is 10.47 Swedish kroner
- show the weight of the diamonds in kilo, 1 carat is 0.0002 kilo

Answer the question:

- At the start of this session, **two ** ways to print all lines
  were shown (`awk '{ print }' coins.txt` and `awk '{ print $0 }' coins.txt`).
  Although they do exactly the same thing, why were both ways shown?
- All the AWK commands are put in single quotes. Why would that be?
  Would double quotes work too?
