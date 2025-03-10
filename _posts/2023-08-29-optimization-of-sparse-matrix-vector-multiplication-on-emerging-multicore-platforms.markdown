---
layout: post
title:  "Paper Review: Optimization of Sparse Matrix-Vector Multiplication on Emerging Multicore Platforms"
date:   2023-08-29 11:48:00 -0600
categories: multicore computing, hpc, paper review
---
[Optimization of sparse matrix-vector multiplication on emerging multicore platforms](https://dl.acm.org/doi/10.1145/1362622.1362674). Samuel Williams, Leonid Oliker, Richard Vuduc, John Shalf, Katherine Yelick, and James Demmel. In Proceedings of the 2007 ACM/IEEE conference on Supercomputing (SC '07). Association for Computing Machinery, New York, NY, USA, Article 38, 1â€“12. DOI:https://doi.org/10.1145/1362622.1362674 
## Summary

This paper evaluates the effect of Spare Matrix Vector Multiplication with state-of-the-art finetuning methods over a range of multicore architectures. The experiments showed that in-order, finegrained multicore processors were much more scalable in terms of performance improvement and energy consumption. The authors suggest that this approach can be a worthwhile approach to uphold, even though it comes at the cost of high latencies at single core level.

## Technical Strengths

1. The paper includes processors that are similar enough to compare, but that are still different enough in specific aspects, which helps the reader gain general insight on how each aspect affects performance.
2. The paper offers detailed theoretical predictions before going into actual results.

## Technical Weaknesses

1. The paper does not offer vertical depth or establish strong relationship between specific processor features and SpMV data characteristics or optimisations.

## Problem or Issue left open

1. The paper applies 8 fine-tuning methods to SpMV, which has its entire section on motivation, however the degree of individual contributions of these methods is not clear through the results.

## Related Readings
* [Niagara: A 32-Way Multithreaded SPARC Processor](https://ieeexplore.ieee.org/document/1453485)., Poonacha Kongetira, Kathirgamar Aingaran, and Kunle Olukotun, IEEE Micro, pp. 21-29, March-April 2005. https://ieeexplore.ieee.org/document/1453485.
* Chapter 2.2 Case Studies of Throughput-oriented CMPs. [Chip Multiprocessor Architecture: Techniques to Improve Throughput and Latency](http://www.morganclaypool.com/doi/pdf/10.2200/S00093ED1V01Y200707CAC003).Kunle Olukotun, Lance Hammond, James Laudon. Synthesis Lectures on Computer Architecture. Morgan Claypool. 2007.