# Regular expressions

!!!- info "Learning outcomes"

    - Practice regular expressions
    - Use two online websites to practice using regular expressions

???- question "For teachers"

    Teaching goals are:

    - The learners have practiced with some regular expressions
    - The learners have used some online websites to learn regular expressions

    Lesson plan:

    * 5 mins: prior knowledge
    * 5 mins: presentation
    * 15 mins: challenge
    * 5 mins: feedback

## Overview

Regular expressions are a used to find patterns in text.
It allows one to express concisely how a piece of text looks like.

For example:

- a common paper size is consists out of a capital A, B or C,
  followed by a number from 1 to and including 9,
  for example `A4`
- [a Swedish personal identity number](https://en.wikipedia.org/wiki/Personal_identity_number_(Sweden)) ('personnummer')
  before 1980 *that is possibly valid* consists of 6 digits, a dash, and then 4 digits,
  for example `890201-3286`
- A blood group is A or B or AB or O, with a plus or minus added for the Rhesus factor,
  for example `AB+`

Knowing regular expressions allows us to search for patterns in a text.

## Exercises

See the exercise procedure [here](../misc/exercise_procedure.md).

### Exercise 1: practice regular expressions

!!!- info "Learning outcomes"

    - Practice the basics of regular expressions

Browse to <https://regexlearn.com> and do exercises 1 to and including 16.

### Exercise 2: practice regular expressions with `regex101.com`

!!!- info "Learning outcomes"

    - Use a character class

A website like used in the previous exercise is useful for learning,
but this is an AWK course, hence we only look for a way to *work with*
regular expressions.

- Browse to <https://regex101.com/> and find in the quick reference
  the character class for a single character 'a, b or c'
- Try out this website: copy the text from 'Three-letter words ending with 'at''
  as is shown below. Use a character class to select all animals

```title="Three-letter words ending with 'at'"
sat
eat
fat
pat
cat
hat
bat
rat
vat
mat
tat
oat
wat
lat
gat
kat
qat
```

> From <https://www.thefreedictionary.com/words-that-end-in-at>

### Exercise 3: practice regular expressions with `regextester.com`

!!!- info "Learning outcomes"

    - Use a word anchor

Here is another website to practice with regular expressions:

- Browse to <https://www.regextester.com/>
  to find a so-called 'anchor' for the end of the string
- Try out this website: copy the text from 'Seven-letter words containing the word 'book''
  as is shown below. Use a word anchor to select all words ending with 'book'

```title="Seven-letter words containing the word 'book'"
booking
booklet
bookman
bookish
logbook
bookend
daybook
nonbook
lawbook
rebooks
prebook
bookful
bookies
bookers
bookmen
bookoos
```

> From <https://www.thefreedictionary.com/words-containing-book>

### Exercise 4: confirming things are true

!!!- info "Learning outcomes"

    - experience the regular expressions in AWK

#### Download the data

In a terminal, do:

```
wget https://github.com/devstronomy/nasa-data-scraper/raw/master/data/csv/satellites.csv
```

to download a file called `satellites.csv`.

This file is a comma-separated file about the planets and
satellites in our solar system.

The dataset has the following columns:

index|name
-----|----------
1    |`planet`
2    |`name`
3    |`gm`
4    |`radius`
5    |`density`
6    |`magnitude`
7    |`albedo`

We do not need to know what all these things mean.

#### match a column element

In a terminal, in the same folder as where the data is downloaded, do:

```
awk -F "," '$2 ~ /on/ { print $0 } ' satellites.csv
```

In English, this is: 'For all lines of which the second column matches the
regex `on`, show the whole line.
Assume that the file uses a comma as a field separator'.

Confirm that this is true.

#### match with a sentence with explicit `$0`

In a terminal, in the same folder as where the data is downloaded, do:

```
awk -F "," '$0 ~ /rth/ { print $0 } ' satellites.csv
```

In English, this is: 'For all lines of which the whole line matches the
regex `rth`, show the whole line.
Assume that the file uses a comma as a field separator'.

Confirm that this is true.

#### match with a sentence with an implicit `$0`

In a terminal, in the same folder as where the data is downloaded, do:

```
awk -F "," '/rth/ { print $0 } ' satellites.csv
```

In English, this is: 'For all lines of which the whole line matches the
regex `rth`, show the whole line.
Assume that the file uses a comma as a field separator'.

Confirm that this is true.

#### Explore the data

Using `awk` only:

- find all the satellites that contain `ir`
- find all the satellites that end with `ir`
- find all the satellites that end with `on` without a vowel (i.e. `aeoui`)
  before `on`. For example: `moon` is invalid, as it has the vowel `o` before `on`
- find all the satellites with a number

Think:

- There are two ways to look for regex matches on a whole sentence
  (`$0 ~ /my_regex/` and `/my_regex/`). Why is it useful to know
  both ways?
