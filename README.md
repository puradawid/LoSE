# LoSE - Laws of Software Engieering

This repository collects all laws that are applicable to software engineering.

## What Is 'Software Engineering'?

Using the definition introduced by Ian Sommervile, software engienering is

> (...) an engineering discipline that is concerned with all aspects of software production from the early stages of system specification through to maintaining the system after it has gone into use. [[Sommerville]]

Based on this definition, software engieering is everything related to the creation or maitenance of software systems of any kind. It assumes there is a certain subset of activities that are common for all software.

## Definitions

### Complication

A matter (a thing or a concept) that has many parts and therefore it's hard to understand it.

Example: a watch, a program, a car

### Complexity

A matter is complex when:
* the same initial state can give different result - for example, 

### Problem

For this document, a problem is a complex matter to solve by a software system. A problem is usually hard to define or describe. Examples: aircraft control, calculator, operating system.

### Program

A set of instructions ran by a computer. A program is usually complicated (can be simple) and run by a single processor - so it's not complex. Program can run other program, subroutine, dynamic library, which sometimes can make it complex (interactions with any program are complex).

### Software System

A set of programs, services, and hardware that solves particular set of problems. Containing complicated programs, the system is usually complex (as their interactions).

## Laws

### Every Program Has Output

The program that has no output (it does not save/print/send any data) has no value and does not exist. There may be a program that takes no initial state ('hello world' is a good example, or a procedure that populates the database with some random data).

### A Single Program Is Complicated But Not Complex

Program, a set of instructions handled by single processor, can be truly complicated, although never complex - for every program, we can define finite set of input events/data that will define the all possible output. In the other words, it's possible to recreate a program state, no matter how complicated, run it and suspect the same results.

### Data (Interations) Can Be Complex

Data is a representation of the reality, which is comlex

Example: a deep learning program is only complicated, but it can find hidden relations in complex data.


[Sommerville]: https://books.google.pl/books?vid=ISBN9780137053469&redir_esc=y
