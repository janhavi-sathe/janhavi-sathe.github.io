---
layout: post
title:  "Paper Review: Reducers and other Cilk++ hyper-objects"
date:   2023-10-03 13:51:00 -0600
categories: multicore computing, hpc, paper review
custom_excerpt: "Introduces hyper-objects as a mechanism to improve parallel performance. Results show improvements over locking and standard C++."
---
[Reducers and other Cilk++ hyperobjects.](http://doi.acm.org/10.1145/1583991.1584017) M. Frigo, P. Halpern, C.E. Leiserson, and S. Lewin-Berlin. In Proceedings of the Twenty-First Annual Symposium on Parallelism in Algorithms and Architectures (Calgary, AB, Canada, August 11 - 13, 2009). SPAA '09. ACM, New York, NY, 79-90.

## Summary:

This paper introduces hyper-objects as a mechanism to improve the parallel performance of program that make use of non-local shared variables between threads by reducing locking overheads, such as lock contention, deadlock, priority inversion, convoying, etc. The paper mainly focuses on a new implementation of Reducers, and briefly covers holders and splitters. The results show that reducers can help improve the performance over locking and standard C++, and is at par with the manual method.

## Strengths:

Improvements made to the reducer are quite useful in improving performance, especially as we increase number of processors.
## Weaknesses:

The deque is more complicated due to removal of `cilk` keyword
## Open Points / Problems:

The paper discusses 3 types of hyper-objects, but more of them can be designed in the future.