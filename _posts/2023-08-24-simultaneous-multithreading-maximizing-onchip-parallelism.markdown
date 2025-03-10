---
layout: post
title:  "Paper Review: Simultaneous Multithreading: Maximizing On-Chip Parallelism"
date:   2023-08-24 14:30:00 -0600
categories: multicore computing, hpc, paper review
---

# Simultaneous Multithreading: Maximizing On-Chip Parallelism
Dean M. Tullsen, Susan J. Eggers, and Henry M. Levy. In Proceedings of the 22nd annual international symposium on Computer architecture (ISCA '95). ACM, New York, NY, USA, 392-403. 1995. DOI=http://dx.doi.org/10.1145/223982.224449 [Link](https://www.princeton.edu/~rblee/ELE572Papers/SMT_Eggers.pdf)
## Summary

This paper studies "simultaneous multi-threading" (SMT) in superscalar processors as a way of reducing vertical & horizontal waste in instruction cycles & reducing bottlenecks. Their analysis focuses on how well this method is able to utilise infrastructure and includes comparisons with alternative organisations viz. a wide superscalar, a fine-grain multithreaded processor, and single-chip, multiple-issue multiprocessing architectures.

The paper also briefly delves into the design complexities introduced by SMT & shared resource contention caused by it, especially in the memory subsystems and offers simplified models which can achieve great performance whilst restraining the complexity to existing levels at the time. The authors also show how properly tuning the cache organization can both increase performance and make individual threads less sensitive to multi-thread contention. Ultimately, the results show that SMT processors have strong potential for better performance with similar number of functional units.

## Strengths

1. The paper provides lot of reasonable bridges between the "current" state of processors to get to SMT processors, with good explanations of why they would be necessary; particularly, the cache requirement analysis is really helpful since memory speed was a critical issue.

## Weaknesses

1. As this paper was published in 1995, it does not really combine the idea of having multiple cores or multiple processors with multi-threading. Both concepts are maintained as rival, distinct concepts, whereas in the time since then, we have seen real, multiplied power by doing both.

## Problems

1. The authors mention - "For this study we have speculated on the pipeline structure for a simultaneous multithreaded processor, since an implementation does not yet exist. (...) Real implementations may see reduced performance due to various design tradeoffs; we intend to explore these implementation issues in future work." 

## Related Readings
* Chapter 5: Simultaneous Multithreading. Multithreading ArchitectureLinks to an external site., Mario Nemirovsky, Dean M. Tullsen. Synthesis Lectures on Computer Architecture. Morgan Claypool. 2013. DOI=https://doi.org/10.2200/S00458ED1V01Y201212CAC021

* The case for a single-chip multiprocessorLinks to an external site. Kunle Olukotun, Basem A. Nayfeh, Lance Hammond, Ken Wilson, and Kunyung Chang. In Proceedings of the seventh international conference on Architectural support for programming languages and operating systems (ASPLOS VII). Association for Computing Machinery, New York, NY, USA, 2–11. DOI:https://doi.org/10.1145/237090.237140
