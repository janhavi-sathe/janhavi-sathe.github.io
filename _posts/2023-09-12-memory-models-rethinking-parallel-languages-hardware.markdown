---
layout: post
title:  "Paper Review: Memory Models: A Case for Rethinking Parallel Languages and Hardware"
date:   2023-09-12 14:03:00 -0600
categories: multicore computing, hpc, paper review
custom_excerpt: "Examines Sequential Consistency with Data Race Free conditions across hardware and software implementations. Proposes future memory models should leverage both programming languages and hardware."
---

[Memory Models: A Case for Rethinking Parallel Languages and Hardware](http://dl.acm.org/citation.cfm?id=1787255) Sarita V. Adve, Hans-J. Boehm. Communications of the ACM, Vol. 53 No. 8, Pages 90-101, August, 2010. 10.1145/1787234.1787255

## Paper Summary

This paper discusses the Sequential Consistency with Data Race Free conditions imposed first in a general context, followed by a description of its evolution through various industry practices. Specifically, it goes over hardware memory models which use fence instructions, Java and C++ memory models which have to compromise security for efficient shared memory and the pros and cons combining hardware and programming level strategies. Finally, based on the all previous memory model implementations, the authors propose that programming languages and hardwares should be used in tandem to implement a more disciplined memory model in the future.

## Strengths

The paper provides solid supporting evidence of where and how each memory models lack to back their criticism.
## Weaknesses

In the suggestions for future paradigm shifts in memory models, the suggestions made seem logically simple and seemingly there is previous work done - but it remains a bit unclear what the known issues with these methods are.
## Open Problems / Issue Left Open

There are popular programming languages such as JavaScript whose memory model is not the same as Java or C/C++ in terms of race semantics, and was not mentioned in this paper.

## Related Readings
* Chapter 3: Memory Consistency Motivation [A Primer on Memory Consistency and Cache Coherence](http://www.morganclaypool.com/doi/pdf/10.2200/S00346ED1V01Y201104CAC016).Daniel J. Sorin, Mark D. Hill, David A. Wood Synthesis Lectures on Computer Architecture. Morgan Claypool. 2011.
* [Shared memory consistency models: a tutorial.](https://ieeexplore.ieee.org/document/546611) S. V. Adve and K. Gharachorloo. Computer, vol. 29, no. 12, pp. 66-76, Dec. 1996, doi: 10.1109/2.546611.