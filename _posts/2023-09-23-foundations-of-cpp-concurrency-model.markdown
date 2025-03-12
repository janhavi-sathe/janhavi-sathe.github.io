---
layout: post
title:  "Paper Review: Foundations of the C++ Concurrency Memory Model"
date:   2023-09-23 13:42:00 -0600
categories: multicore computing, hpc, paper review
custom_excerpt: "Introduces the C++ memory model which introduces constructs for parallel programming in the C++ language standard. A key takeaway from this paper is the discussion surrounding atomic memory operations at hardware level, its cost, issues in synchronisation as well as differences from software counterpart keyword `atomic`."
---
## Foundations of the C++ Concurrency Memory Model
[Foundations of the C++ Concurrency Memory Model](http://doi.acm.org/10.1145/1375581.1375591), H. Boehm, and S. V. Adve. In Proceedings of the 2008 ACM SIGPLAN Conference on Programming Language Design and Implementation (Tucson, AZ, USA, June 07 - 13, 2008). PLDI '08. ACM, New York, NY, 68-78. DOI= http://doi.acm.org/10.1145/1375581.1375591

## Summary
This paper introduces the C++ memory model which introduces constructs for parallel programming in the C++ language standard itself. The new model is based on the then-latest Java memory model which brought data race free semantics for multithreaded applications to  the mainstream, with a few modifications to account for the issues that surfaced from the Java model, such as preventing certain optimizations, higher complexity. A key takeaway from this paper is the discussion surrounding atomic memory operations at hardware level, its cost, issues in synchronisation as well as differences from software counterpart keyword "atomic". They also discuss how improve the efficiency of Trylock by modifying its specification so that it is not guaranteed that the operation will succeed just because the lock is available.

## Strengths:

Model complexity is greatly reduced by the new model.
## Weaknesses:

Though there are known implementation issues caused by sequential consistency for data race free programs, as done by Java, the C++ model continues to insist on it in most cases.
## Open Issues / Problems:

The model proposed is more theoretical, and not implemented yet, so it would need to be tested further in order to have practical evidence supporting all the claims made here.