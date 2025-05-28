# Associative arrays

!!!- info "Learning outcomes"

    - work with associative arrays

???- question "For teachers"

    Teaching goals are:

    - Learners work with associative arrays
    - Learners can get the unique elements of a column
    - Learners can make a tally of a column

    Lesson plan:

    * 5 mins: prior knowledge
    * 5 mins: presentation
    * 15 mins: challenge
    * 5 mins: feedback

## Overview

In this session, we work with associative arrays.
Associative arrays are used in, among others,
to find the (unique) values in a column and to create a tally.

## Exercises

See the exercise procedure [here](../misc/exercise_procedure.md).

### Exercise 1: confirming things are true

!!!- info "Learning outcomes"

    - experience variables

#### Download the data

In a terminal, do:

```bash
wget https://raw.githubusercontent.com/richelbilderbeek/awk_course/master/data/diamonds_no_header.tsv
```

to download a file called `diamonds_no_header.tsv`.

#### Write to and read from an associative array

In a terminal, in the same folder as where the data is downloaded, do:

```bash
awk 'BEGIN { counts["ideal"] = 12345 } END { print counts["ideal"] }' diamonds_no_header.tsv
```

In English, this is: 'At the start, in the `counts` array, at element `ideal`,
store the value `12345`. In the end, if the `counts` array, show the
value at element `ideal`.

Confirm that this is true.

#### Get a count

In a terminal, in the same folder as where the data is downloaded, do:

```bash
awk '{ counts[$2] = counts[$2] + 1 } END { print counts["ideal"] }' diamonds_no_header.tsv
```

In English, this is: 'For every line, in the `counts` array,
at the element in the second column, increase the value by one.
In the end, if the `counts` array, show the
value at element `ideal`.

Confirm that this is true.

#### Get a count again

In a terminal, in the same folder as where the data is downloaded, do:

```bash
awk '{ counts[$2] += 1 } END { print counts["ideal"] }' diamonds_no_header.tsv
```

In English, this is: 'For every line, in the `counts` array,
at the element in the second column, increase the value by one.
In the end, if the `counts` array, show the
value at element `ideal`.

Confirm that this is true.

#### Get a count again again

In a terminal, in the same folder as where the data is downloaded, do:

```bash
awk '{ counts[$2]++ } END { print counts["ideal"] }' diamonds_no_header.tsv
```

In English, this is: 'For every line, in the `counts` array,
at the element in the second column, increase the value by one.
In the end, if the `counts` array, show the
value at element `ideal`.

Confirm that this is true.

#### Get a count again again again

In a terminal, in the same folder as where the data is downloaded, do:

```bash
awk '{ ++counts[$2] } END { print counts["ideal"] }' diamonds_no_header.tsv
```

In English, this is: 'For every line, in the `counts` array,
at the element in the second column, increase the value by one.
In the end, if the `counts` array, show the
value at element `ideal`.

Confirm that this is true.

#### Show all elements

In a terminal, in the same folder as where the data is downloaded, do:

```bash
awk '{ counts[$2]++ } END { for (count in counts) print count }' diamonds_no_header.tsv
```

In English, this is: 'For every line, in the `counts` array,
at the element in the second column, increase the value by one.
In the end, show all elements of the array `counts`.

Confirm that this is true.

#### Show all values

In a terminal, in the same folder as where the data is downloaded, do:

```bash
awk '{ counts[$2]++ } END { for (count in counts) print counts[count] }' diamonds_no_header.tsv
```

In English, this is: 'For every line, in the `counts` array,
at the element in the second column, increase the value by one.
In the end, of all elements of the array `counts`, show their values.

Confirm that this is true.

#### Show all elements and values

In a terminal, in the same folder as where the data is downloaded, do:

```bash
awk '{ counts[$2]++ } END { for (count in counts) print count ": " counts[count] }' diamonds_no_header.tsv
```

In English, this is: 'For every line, in the `counts` array,
at the element in the second column, increase the value by one.
In the end, show all elements of the array `counts` and their respective values.

Confirm that this is true.

### Exercise 2: explore data

#### Download the data

In a terminal, do:

```bash
wget https://raw.githubusercontent.com/tidyverse/ggplot2/main/data-raw/mpg.csv
```

to download a file called `mpg.csv.csv`.

This file is a tab-separated file about diamonds and
is part of the `ggplot2` R package.

* [Raw data](https://raw.githubusercontent.com/tidyverse/ggplot2/main/data-raw/mpg.csv)
* [Data description](https://ggplot2.tidyverse.org/reference/diamonds.html)

The dataset has the following columns:

Index|Column name   |Description
-----|--------------|-----------------
 1   |`manufacturer`|manufacturer name
 2   |`model`       |model name
 3   |`displ`       |engine displacement, in litres
 4   |`year`        |year of manufacture
 5   |`cyl`         |number of cylinders
 6   |`trans`       |type of transmission
 7   |`drv`         |the type of drive train, where f = front-wheel drive, r = rear wheel drive, 4 = 4wd
 8   |`cty`         |city miles per gallon
 9   |`hwy`         |highway miles per gallon
10   |`fl`          |fuel type
11   |`class`       |type of car

#### Explore the data

Using `awk` only:

* show if the data has a header yes/no
* show the number of cars in the dataset
* show the number of columns in the dataset
* show all the car manufacturers' names
* per car manufacturer, show the number of cars it produces
* show the lowest city miles per gallon
* show the highest city miles per gallon, in city miles per liter.
  Assume a gallon, is a US gallon. A US gallon is 3.785411784 liter
* find the type (i.e. in the last column) of car that spends the least fuel on the highway
* imagine you have each of these cars once. You want each of them to
  drive one city mile. How much gallons of fuel do you need?
* imagine you have each of these cars once. You want each of them to
  drive one city mile. How much gallons of each type of fuel do you need?

Think:

* There are multiple way to increase an element in an array by one.
  Why so many? Is there a difference?
