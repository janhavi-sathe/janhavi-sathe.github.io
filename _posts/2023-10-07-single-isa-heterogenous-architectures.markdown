---
layout: post
title:  "Paper Review: Single-ISA Heterogeneous Multi-Core Architectures: The Potential for Processor Power Reduction"
date:   2023-10-07 23:19:00 -0600
categories: multicore computing, hpc, paper review
custom_excerpt: "Introduced a heterogenous, single instruction set architecture with by utilizing cores with different properties, with the goal of increasing energy efficiency of chips. Results generally show major improvements in energy consumption with only minor performance sacrifices."
---

[Single-ISA Heterogeneous Multi-Core Architectures: The Potential for Processor Power Reduction](https://www.microarch.org/micro36/html/pdf/kumar-SingleISAHeterogen.pdf). Rakesh Kumar, Keith I. Farkas, Norman P. Jouppi, Parthasarathy Ranganathan, Dean M. Tullsen.  Proceedings. 36th Annual IEEE/ACM International Symposium on Microarchitecture, 2003. MICRO-36., 2003, pp. 81-92, doi: 10.1109/MICRO.2003.1253185.

## Summary:

The authors present a multi-core processor architecture that utilises heterogenous cores with specialized characteristics such as in-order vs out-of-order execution, wide-issue vs single-issue, combined through modified interfaces. This architecture is motivated by the logic that widely varying applications have widely varying processor requirements, which if not met can cause higher energy overheads. The results vary based on the choice of cores and objective function implemented, but overall show that major improvements in energy consumption are possible with relatively smaller performance sacrifices.

## Strengths:

The effectiveness of this method is quite apparent through the results and well-explained
## Weaknesses:

This method introduces design and verification overheads which will increase with the number of cores supported.
## Open Points / Problems:

If objective functions are allowed to change over time, or if the applications are more varied than the experiments here, wider heterogeneity in cores could be necessary.

## Related Reading
* [Single-ISA heterogeneous multi-core architectures for multithreaded workload performance](https://ieeexplore.ieee.org/stamp/stamp.jsp?arnumber=1310764). R. Kumar, D. M. Tullsen, P. Ranganathan, N. P. Jouppi and K. I. Farkas. Proceedings. 31st Annual International Symposium on Computer Architecture, 2004., 2004, pp. 64-75, doi: 10.1109/ISCA.2004.1310764.