---
layout: post
title:  "Paper Review: Hoard: A Scalable Memory Allocator for Multithreaded Applications"
date:   2023-10-16 18:23:00 -0600
categories: multicore computing, hpc, paper review
custom_excerpt: "Introduces 'Hoard' memory allocator design which focuses on tackling false sharing on shared cache lines and blowup to improve scalability, memory efficiency and speed. Hoard's key feature is that it uses a global heap and a processor-local heap."
---
[Hoard: a scalable memory allocator for multithreaded applications](https://people.cs.umass.edu/~emery/pubs/berger-asplos2000.pdf). Emery D. Berger, Kathryn S. McKinley, Robert D. Blumofe, and Paul R. Wilson. In Proceedings of the 9th Intl. Conf. on Architectural Support for Programming Languages and Operating Systems (ASPLOS IX). Association for Computing Machinery, New York, NY, USA, 117–128.  2000. 
[https://doi.org/10.1145/378993.379232](https://doi.org/10.1145/378993.379232)

## Summary

In this papers, the authors introduce "Hoard" memory allocator design which focuses on tackling false sharing on shared cache lines and blowup to improve scalability, memory efficiency and speed. Hoard's key feature is that it uses a global heap and a processor-local heap, dynamically allocating free memory to both as needed. Hoard was tested on eleven programs, fourteen processors and compared with previous best performing serial & concurrent allocator and in all cases it shows substantial improvements. 

## Strengths:

* The design mitigates the problem of blowup substantially, which was known but never properly addressed by previous memory allocator designs. 
## Weaknesses:

* Hoard's logic for de-allocating processor heap memory when it falls below a certain threshold would not work well for programs that have a large range of memory requirements, or that requires sudden spikes of memory unexpectedly, as shown on espresso and shbench.  
## Open Points / Problems:

* The authors mention several open problems for this first version of Hoard, one of which is exploring ways to improve performance of Hoard on cc/NUMA architectures.

## Related Reading
* [Scalable lock-free dynamic memory allocation ](https://www.cs.tufts.edu/~nr/cs257/archive/neal-glew/mcrt/Non-blocking%20data%20structures/p35-michael.pdf). Maged M. Michael. In Proceedings of the ACM SIGPLAN 2004 conference on Programming language design and implementation (PLDI '04). Association for Computing Machinery, New York, NY, USA, 35–46. [ https://doi.org/10.1145/996841.996848Links to an external site.
](https://doi.org/10.1145/996841.996848)