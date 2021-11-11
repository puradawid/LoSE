# LoSE - Laws of Software Engieering

This repository collects all laws that are applicable to software engineering.

The laws below has been elicited from software engineer's experience and literature available. They are never finished, never accurate, but good enough to be used by people that develop, test and maintain software around the world.

## What Is 'Software Engineering'?

Using the definition introduced by Ian Sommervile, software engienering is

> (...) an engineering discipline that is concerned with all aspects of software production from the early stages of system specification through to maintaining the system after it has gone into use. [^Sommerville]

Based on this definition, software engieering is everything related to the creation or maitenance of software systems of any kind. It assumes there is a certain subset of activities that are common for all software.

## Definitions

### Complication

A matter (a thing or a concept) that has many parts and therefore it's hard to understand it. It is realtively easy to reproduce the same results knowing only on the inputs.

Examples: a watch, a program, a car

### Complexity

A matter is complex when:
* the same initial state (inputs) can give different result
* elements (agents) of the system are less important than interactions between them (i.e. you can't just sum up agents' abilities)
* to understand the matter and forecast its behaviour, one has to perform experiments (it cannot be understood by just dissasembling)

Examples: single cell, weather, human interactions, politics

### Problem

For this document, a problem is a complex matter to solve by a software system. A problem is usually hard to define or describe. Examples: aircraft control, calculator, operating system.

### Program

A set of instructions ran by a computer. A program is usually complicated (can be simple) and run by a single processor - so it's not complex. Program can run other program, subroutine, dynamic library, which sometimes can make it complex (interactions with any program are complex).

### Software System

A set of programs, services, and hardware that solves particular set of problems. Containing complicated programs, the system is usually complex (as their interactions).

## Laws

### Every Program Has An Output

The program that has no output (it does not save/print/send any data) has no value and does not exist. There may be a program that takes no initial state ('hello world' is a good example, or a procedure that populates the database with some random data).

Consequences:
* testing software is always based on output verification against the inputs
* finishing the program is also an output. Consider the program that finishes after some time - but returns nothing. Is this a single output? Can it fail?
* any set of instructions that produces no output is not a program and can be removed

The law gives you a perspective of testing and designing certain functionallity, i.e. from 10k feet perspective an engineer should focus about predicting outputs the most. Additionally, the output is very detailed, and usually much more than one response. Consider a program that returns random numbers. What is the output? It can be just the number, but in certain situations the time it takes to randomize it is also an output, or maybe there is an interim data processing left somewhere in hard drive? From engineer's perspective, all of those has to be reviewed and classified as important, ignored or irrelevant.

### A Single Program Is Complicated But Not Complex

Program, a set of instructions handled by single processor, can be truly complicated, although never complex - for every program, we can define finite set of input events/data that will define the all possible output. In the other words, it's possible to recreate a program state, no matter how complicated, run it and suspect the same results.

Thus, all programs are verifiable by set of tests in form of inputs against outputs. For instance, a program that increments input could be verified with:

* input: 10, output: 11
* input: 11, output 12
* input: 100, output 101
* input: MAX_INT, output: ERROR

In this case, the input starts with -MAX_INT until MAX_INT. An engineer can verify how many of those tests should be performed to verify the program's correctness.

### Data (Interations) Can Be Complex

Data is a representation of the reality, which is (usually complex).

Example: a deep learning program is only complicated, but it can find hidden (unexpected) relations in complex data.

[^Sommerville]: Ian Sommerville, *Software Engineering* 10th edition, Pearson https://books.google.pl/books?vid=ISBN9780137053469&redir_esc=y
