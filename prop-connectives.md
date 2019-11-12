---
layout: default
title: "Propositional Logic"
description: "Propositional Connectives"
---

<script>
  MathJax = {
    tex: {inlineMath: [['$', '$'], ['\\(', '\\)']]}
  };
  </script>
  <script id="MathJax-script" async src="https://cdn.jsdelivr.net/npm/mathjax@3/es5/tex-chtml.js"></script>



# Propositional connectives and truth-tables

## Goals today

-   The basic idea of propositional logic.
-   The propositional connectives and their truth-tables.
-   Translating into propositional logic.

## Basic idea of propositional logic

-   Propositional logic is a logic which takes as its most
    primitive unit *the proposition*.
-   A proposition is something that can be true or false. Examples
    - "The snow is white."
    - "Bill Clinton was governor of Missouri."
-   To take propositions as a *primitive* means that, within this logic,
    there are some propositions which we regard as not having any
    further logical structure.

## Logical Structure

-   Consider again the examples:
    - "The snow is white."
    - "Bill Clinton was governor of Missouri."
-   Contrast these to:
  - "The snow is white *or *the snow is *not* white."
  - "*If* Bill Clinton was governor of Missouri *then* he was a fan of the St. Louis Cardinals *and* he lived in Jefferson city."
-   These latter propositions seem to be built up from smaller
    propositions by means of logical operations such as *or*, *not*,
    *and*," *if* . . . *then*. . . "
-   So in propositional logic, the idea is to take some propositions as
    basic \-- having no further structure \-- and looking at the way in
    which we build further propositions with these logical operations.

## Why would you want to do that?

-   One of the topics of logic is validity. One way to try to characterize validity is in terms of
    truth-preservation: *whenever* the premises are true, then the
    conclusion is true.
-   One of the aims of logic is to develop ways of *showing* that
    certain arguments are *valid* and that others are invalid.
-   By focusing on sentences built up from basic propositions and the
    logical operations, this reduces to the task of determining the
    truth of the basic propositions and *understanding how logical
    operations interact with truth-values*.


## Conjunction

-   If $P$, $Q$ are both propositions, then "$P$ *and $Q$" is a third proposition.
-   The symbol for "and" is $\wedge$. It looks like the carrot ^ symbol but written lower down on the line.
-   Another common symbol is &.
-   INSERT remark about `/\`.
-   For instance, take *P* to be "Alice attends the meeting," and take *Q* to be "Bill attends
        the meeting". Then $P\wedge Q$ is ``Alice attends the meeting and Bill attends the meeting.''
-  The following table indicates when $P\wedge Q$ is true, as function of when $P$ is true and when $Q$ is true.

~~~{.TruthTable .Simple options="strictGivens autoAtoms nocounterexample nocheck" submission="none"}
ConjunctionTable P/\Q
|   T T T
|   T F F
|   F F T
|   F F F
~~~

<iframe src="https://carnap.io/shared/walsh@g.ucla.edu/Week01-exc"></iframe>
