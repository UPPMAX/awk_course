# AWK course

This module introduces the fundamentals of the AWK language. 

!!! info "Content"

    This is the teaching material for the UPPMAX AWK course.

    This repository is based on the material of <https://pmitev.github.io/to-awk-or-not/>
    and puts it into teaching cycles.
    
## Schedule

Time          | Topic
--------------|-------------------------------
13:00-14:00   | [Regular expressions](regexps.md)
14:00-14:15   | Break
14:15-15:00   | [What is AWK](what_is_awk.md), [Basic Linux](basic_linux.md)
15:00-16:00   | Break
15:15-16:00   | [Related tools](related_tools.md)

## Overview

### Facets of AWK

```mermaid
flowchart TD

  print[Print]
  filtering_on_values[Filtering on values]
  begin_and_end[BEGIN and END]
  variables[Variables]
  associative_arrays[Associative arrays]
  filtering_on_regex[Filtering on regular expressions]
  comma_as_separator[Comma as a separator]

  %% Facets of AWK
  filtering_on_values --> |needs| print
  comma_as_separator --> |needs| print
  begin_and_end --> |needs| filtering_on_values
  variables --> |needs| begin_and_end
  associative_arrays --> |needs| variables
  filtering_on_regex --> |needs| filtering_on_values
```

### AWK as a programming language

```mermaid
flowchart TD

    %% Give a white background to all nodes, instead of a transparent one
    %% classDef node fill:#fff,color:#000,stroke:#000
    classDef focus_node fill:#fff,color:#000,stroke-width:4px

    subgraph interpreters[Interpreters]
    awk
    gawk
    gnu_awk[GNU Awk]
    interpreter
    end

    subgraph programming_languages[Programming languages]

      subgraph compiled_languages[Compiled languages]
        compiled_language[Compiled language]
      end

      subgraph interpreted_languages[Interpreted languages]
        interpreted_language[Interpreted language]
        AWK:::focus_node
      end
    end

    interpreted_language --> |is run by| interpreter
    interpreted_language <--> |is not| compiled_language
    awk --> |is a| interpreter
    gawk --> |is a| interpreter    
    gawk --> |is an abbreviation of| gnu_awk

    AWK --> |is a| interpreted_language

```

### AWK and its friends

```mermaid
flowchart TD

  classDef focus_node fill:#fff,color:#000,stroke-width:4px

  awk:::focus_node
  cut
  grep
  join
  sed
  tr
  wc

  regexps[Regular expressions]
  split_data_in_columns[Split data into columns]
  count[Count]
  merge_tables[Merge tables]
  replace[Replace]

  %% Tools
  awk --> |can do| regexps
  sed --> |can do| regexps
  grep --> |can do| regexps

  awk --> |can do| split_data_in_columns
  cut --> |can do| split_data_in_columns

  awk --> |can do| count 
  wc --> |can do| count

  awk --> |can do| replace
  tr --> |can do| replace
  sed --> |can do| replace

  join --> |can do| merge_tables
```

## Links

 * [CLI text processing with GNU awk](https://learnbyexample.github.io/learn_gnuawk/): a book we use
 * [To awk or not](https://pmitev.github.io/to-awk-or-not): course material we use

