---
layout: post
title:  "Paper Review: Multicore Desktop Programming with Intel Threading Building Blocks"
date:   2023-10-12 08:36:00 -0600
categories: multicore computing, hpc, paper review
custom_excerpt: ""
---
[Multicore Desktop Programming with Intel Threading Building Blocks](https://ieeexplore.ieee.org/stamp/stamp.jsp?tp=&arnumber=5672517) W. Kim and M. Voss. IEEE Software, vol. 28, no. 1, pp. 23-31, Jan.-Feb. 2011, doi: 10.1109/MS.2011.12.
## Summary

This article talks about Intel's Threading Building Blocks (TBB) which is C++ template library which is based on a task-based, modular programming model that uses a work-stealing algorithm for developing composable execution environments for desktop applications. The article describes the Task Interface, Scheduling implemented by TBB as well as the in-built parallel programs, types of concurrent, synchronisation containers present and other tools, viz. mutex/lock mechanisms, atomic template class and thread-local storage. Although a detailed performance analysis is not provided, included graph shows linearly increasing speed-up as the number of cores increased.

## Strengths

* Article provides clear, accessible overview of the Intel TBB's salient features and when to use them.
## Weaknesses

* Performance section is quite sparse - only 3 programs were shown, which all implement parallel algorithms, and no explanation or interpretation of the performance was given.
* There is no supporting evidence provided on how Intel TBB helps in running several heterogenous applications simultaneously, which was the problem established at the start of the article.
## Open Points / Problems:

* It would be useful to explore how much the target machine's memory specs affect the performance improvements of TBB, as in several places, for simplicity, the authors have assumed it works in an ideal fashion.

## Related Reading
* [RAJA: Portable Performance for Large-Scale Scientific Applications.](https://cs.millersville.edu/~wkillian/files/RAJA.P3HPC-SC19.pdf) D. A. Beckingsale et al. IEEE/ACM International Workshop on Performance, Portability and Productivity in HPC (P3HPC), Denver, CO, USA, 2019, pp. 71-81, doi: 10.1109/P3HPC49587.2019.00012.
* [Kokkos: Enabling performance portability across manycore architectures.](https://www.osti.gov/servlets/purl/1143842) H. Carter Edwards and Christian R. Trott.2013 Extreme Scaling Workshop (xsw 2013), Boulder, CO, 2013, pp. 18-24, doi: 10.1109/XSW.2013.7.