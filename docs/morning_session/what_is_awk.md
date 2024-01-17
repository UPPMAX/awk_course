# What is Awk

!!!- info "Learning objectives"

    * To be able to login to Rackham autonomously
    * To be able to load a Python version autonomously
    * To be able to run a minimal Python program autonomously

???- question "For teachers"

    Teaching goals are:

    - Learners have used the UPPMAX documentation
    - Learners have used the Python interpreter
    - Learners have loaded Python using the module system

    Other goals are:

    - Verify that learners indeed have learned how to login
    - Verify that learners indeed have learned how to use the module system

    Lesson plan:

    * 5 mins: prior knowledge
    * 5 mins: presentation
    * 15 mins: challenge
    * 5 mins: feedback

## Overview

To develop code in Python on the UPPMAX clusters, one needs to:

- Login to Rackham, to be on an UPPMAX cluster
- Load the Python module, to be able to use a modern Python interpreter
- Use the Python interpreter, to run Python code

Luckily, UPPMAX has documentation that should allow you to do so autonomously.

These exercises will ensure you are able to run a minimal Python program.

```mermaid
flowchart TD
    python[[Python]]

    %% Give a white background to all nodes, instead of a transparent one
    classDef node fill:#fff,color:#000,stroke:#000

    subgraph sub_programming_language[Python as a language]
      interpreted_language[Interpreted language]
      programming_language[Programming language]
      scripting_language[Scripting language]
      interpreter[Interpreter]
      %% scripts[Scripts]
      %% text_files[Text files]
    end
    style sub_programming_language fill:#ccf,color:#000,stroke:#fcc


    subgraph sub_uppmax[UPPMAX]
      uppmax[UPPMAX]
      uppmax_modules[UPPMAX modules]
      uppmax_clusters[UPPMAX clusters]
      %% text_editors[Text editors]
      %%x_forwarding[X-forwarding]
      %%remote_desktop[Remote desktop]
    end
    style sub_uppmax fill:#fcc,color:#000,stroke:#fcc

    python --> |is a| programming_language
    python --> |is a| interpreted_language
    python --> |is a| scripting_language

    %% programming_language --> |uses| text_files
    interpreted_language --> |has a| interpreter
    scripting_language --> |is a|interpreted_language
    %% scripting_language --> |runs| scripts
    %% scripts --> |are| text_files
    %% scripts --> |can use| command_line_arguments

    uppmax --> |has| uppmax_clusters
    uppmax_clusters --> |have| uppmax_modules
    %%uppmax_clusters --> |have| text_editors
    %%uppmax_clusters --> |allow| x_forwarding
    %%uppmax_clusters --> |has| remote_desktop
    %% uppmax_modules --> |allow the use of| python_packages
    uppmax_modules --> |allow the use of| interpreter

    %% text_editors --> |work on|text_files
    %%x_forwarding --> |allows|graphics
    %%remote_desktop --> |allows|graphics
    

    %% variables ~~~ uppmax
```

## Exercises

### Exercise procedure

???- info "For teachers"

    > You will be put into Zoom Breakout rooms, in random pairs.
    > One should share his/her screen and do the exercises together on that computer.

    This assures everyone learns effectively: pairs are optimal.

    Check if every room has a screen that is shared!

    > There is no silent room.

    There is no silent room, as:
 
    - (1) working in pairs allows 'Think, Pair, Share' to work; answering is not personal anymore, 
    - (2) getting the experienced learners to teach makes them learn too,
    - (3) this does not work well with Zoom assigning random pairs, 
    - (4) this is not designed to be a self-study course

    > When done with the exercises, go back to the main room

    This helps set the pace of the course. 

    If two-thirds of the learners are back, call back all learners.

    > Breaks are always on the scheduled time. You will be reminded in that chat

    Breaks are important. 

    > Take that break, either in the main room or in your breakout room. The breakout rooms will not be closed

    Do not disrupt the flow (even more) by closing the breakout rooms.

    > In the main room, random learners will be asked questions
    > regarding those exercises.
    > Say the answer you agreed upon as a group (i.e. not your personal answer!)

    This is form is described as 'Think, Pair, Share' in 'The Fundamentals
    of Teaching' by Mike Bell

- You will be put into Zoom Breakout rooms, in random pairs.
- There is no silent room.
- One should share his/her screen and do the exercises together on that computer
- When done with the exercises, go back to the main room
- Breaks are always on the scheduled time. You will be reminded in that chat
- Take that break, either in the main room or in your breakout room. The breakout rooms will not be closed
- In the main room, random learners will be asked questions
  regarding those exercises.
  Say the answer you agreed upon as a group (i.e. not your personal answer!)

### Exercise 1: login to Rackham

!!!- info "Learning objectives"

    - to be able to login to Rackham autonomously

Login to Rackham from your terminal. 
This is described at the UPPMAX page 'Login to Rackham' [here](http://docs.uppmax.uu.se/getting_started/login_rackham/).

### Exercise 2: load the Python module

!!!- info "Learning objectives"

    - to be able to load a Python version autonomously

Load Python version 3.10.8. 
This is described at the UPPMAX pages on Python [here](http://docs.uppmax.uu.se/software/python/).

### Exercise 3: write a 'Hello world' program

!!!- info "Learning objectives"

    - to be able to run a minimal Python program autonomously

Start Python and write a 'Hello world' program.
This is described at the UPPMAX pages on Python programming [here](http://docs.uppmax.uu.se/software/python_programming/#use-the-python-interpreter)
