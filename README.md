# LoSE - Laws of Software Engineering

This repository collects laws applicable to software engineering.

The laws below have been elicited from software engineers' experience and the literature available. They are never finished, never accurate, but good enough to be used by people that develop, test and maintain software around the world.

## What Is 'Software Engineering'?

Using the definition introduced by Ian Sommerville, software engineering is

> (...) an engineering discipline that is concerned with all aspects of software production from the early stages of system specification through to maintaining the system after it has gone into use. [^Sommerville]

Based on this definition, software engineering is everything related to the creation or maintenance of software systems of any kind. It assumes there is a certain subset of activities that are common for all software.

## Definitions

### Complicated (thing)

A matter is complicated when it is:

> involving a lot of different parts, in a way that is difficult to understand[^complicated_dict]

If the matter is complicated but not complex, the same initial state gives the same results every time.

Examples: a watch, a program, a car

### Complex (thing)

A matter is complex when it is:

> having many parts related to each other in ways that may be difficult to understand[^complex_dict]

The difference between complicated and complex is subtle from these definitions. In both cases, things are hard to understand, but in a complex matter, relations between elements (despite how simple they are to understand) are key to the system - in the other words, different relations between elements makes the thing different.

There are several consequences of having complex matter compared to the complicated one:
* the same initial state (inputs) can give a different result
* elements (agents) of the system are less important than interactions between them (i.e. you can't just sum up agents' abilities)
* to understand the matter and forecast its behaviour, one has to perform experiments (it cannot be understood by just disassembling)

Examples: a single cell, weather, human interactions, politics

### Problem

For this document, a problem is a complex matter to solve by a software system. A problem is usually hard to define or describe. Examples: aircraft control, calculator, operating system.

### Program

A set of instructions ran by a computer. A program is usually complicated (can be simple) and run by a single processor - so it's not complex. A program can run another program, subroutine, dynamic library, which sometimes can make it complex (interactions with any program are complex).

### Software System

A set of programs, services, and hardware that solves a particular set of problems. Containing complicated programs, the system is usually complex (as their interactions).

## Laws

### Every Program Has An Output

The program that has no output (it does not save/print/send any data) has no value and does not exist. There may be a program that takes no initial state ('hello world' or a procedure that populates the database with some random data are good examples).

#### Consequences

* testing software is always based on output verification against the inputs
* finishing the program is also an output. Consider the program that finishes after some time - but returns nothing. Is this a single output? Can it fail?
* any set of instructions that produces no output is not a program and can be removed
* there is an infinite number of programs that have no outputs

The law gives you a perspective of testing and designing certain functionality, i.e. from a 10k feet perspective an engineer should focus on predicting outputs the most. Additionally, the output is very detailed, and usually much more than one response. Consider a program that returns random numbers. What is the output? It can be just the number, but in certain situations, the time it takes to randomize it is also an output, or maybe there is an interim data processing left somewhere in the hard drive? From an engineer's perspective, all of those has to be reviewed and classified as important, ignored or irrelevant.

#### Counterexample

Imagine a program that has no output. This program cannot be verified in any case, because it cannot end. Therefore, such a program cannot be created or may even exist. It is easy to assume, there is an infinite number of programs without inputs running at this moment - and still, we cannot verify their existence.

### A Single Program Is Complicated But Not Complex

A program, a set of instructions handled by a single processor, can be truly complicated, although never complex - for every program, we can define a finite set of input events/data that will define all possible output. In the other words, it's possible to recreate a program state, no matter how complicated, run it and suspect the same results.

Thus, all programs are verifiable by a set of tests in form of inputs against outputs. For instance, a program that increments input could be verified with:

* input: 10, output: 11
* input: 11, output 12
* input: 100, output 101
* input: MAX_INT, output: ERROR

In this case, the input starts with -MAX_INT until MAX_INT. An engineer can verify how many of those tests should be performed to verify the program's correctness.

Due to the high level of a program's complication, sometimes, engineers decide to treat the program as a complex matter by ignoring certain output or making it "irrelevant", when in fact it is the opposite. Then, they run into a situation where they perform black-box experiments against the complicated program. This is a sub-optimal situation, and engineers should be aware of the certain field they can improve.

### Data (Interations) Can Be Complex

Data is a representation of reality, which is (usually complex).

Example: a deep learning program is only complicated, but it can find hidden (unexpected) relations in complex data.

[^Sommerville]: Ian Sommerville, *Software Engineering* 10th edition, Pearson https://books.google.pl/books?vid=ISBN9780137053469&redir_esc=y
[^complicated_dict]: https://dictionary.cambridge.org/dictionary/english/complicated
[^complex_dict]: https://dictionary.cambridge.org/dictionary/english/complex
