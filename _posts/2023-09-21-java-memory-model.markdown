---
layout: post
title:  "Paper Review: Java Memory Model"
date:   2023-09-21 13:08:00 -0600
categories: multicore computing, hpc, paper review
custom_excerpt: "Introduces Java 5.0's new Memory Model with explicit rules for synchronized programs and guarantees against out-of-thin-air values. Presents both a simplified 'Happens-before' model and formal specifications."
---
## The JAVA Memory Model
[The Java Memory Model](http://doi.acm.org/10.1145/1040305.1040336), J. Manson, W. Pugh, and S. V. Adve. In Proceedings of the Symposium on Principles of Programming Languages (PoPL), January 2005.

## Summary

This paper introduces the features of the new Java Memory Model introduced with Java 5.0 which provides more explicit rules about what a correctly synchronised (data-race-free) program should do, and strong guarantees against out-of-thin-air values that will not compromise on the required security standards. The authors first present a simplified version of the model, called "Happens-before" model, and illustrate why it needs additional clauses for causality. The authors then present a formal, notational description of the rules along with an example. Finally, the authors discuss the impact of the new model for implementors of and programmers using the Java platform.

## Strengths

The authors provide both mathematical descriptions, proofs and examples in plain English for the specification.
## Weaknesses

In the "Surprising and Controversial Behaviours" section, a little more examples and discussion on the effects of arbitrary decisions would have been helpful.
## Problem / Issue left open

The authors chose to not discuss the changes in the treatment of final fields and finalisation/garbage collection to not lengthen the paper too much. 