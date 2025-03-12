---
layout: post
title:  "Paper Review: The Implementation of the Cilk-5 Multithreaded Language"
date:   2023-09-28 13:36:00 -0600
categories: multicore computing, hpc, paper review
custom_excerpt: "Presents the language redesigns and runtime systems modifications introduced in Cilk-5 in order to make it simplify it, as well as to increase efficiency. present a novel 'two clone' compilation strategy when compiling Cilk to C. Results show that the implementation of the work-first principle is successful."
---
[The Implementation of the Cilk-5 Multithreaded Language](http://doi.acm.org/10.1145/277650.277725) by Matteo Frigo, Charles E. Leiserson, and Keith H. Randall. 1998 ACM SIGPLAN Conference on Programming Language Design and Implementation (PLDI), Montreal, Canada, June 1998.
## Summary:

This paper presents the language redesigns and runtime systems modifications introduced in Cilk-5 in order to make it simplify it, as well as to increase efficiency. One major strategy change that was implemented, based on theoretical analysis of the previous scheduling algorithm, was to shift the overheads to the critical path and reduce all work overheads as fast as possible. This is known as the work-first principle, which the authors exploit in order to present a novel "two clone" compilation strategy when compiling Cilk to C. The results show that Cilk-5 does successfully employ the work-first principle, without significantly compromising the ability of Cilk applications to scale up. 

## Strengths:

Authors present strong theoretical analysis for making the required changes.
The assumptions made are all validated by the results.
## Weaknesses:

It seems as though the optimisations don't work as well if serialised algorithms are converted to parallel before implementing, and no generalised explanation is provided for why that's happening
## Open Issues / Problems:

In case a C elision is not available for comparison, there should be an alternative method to measure relative performance