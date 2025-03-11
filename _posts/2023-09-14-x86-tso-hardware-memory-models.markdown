---
layout: post
title:  "Paper Review: x86-TSO: A Rigorous and Usable Programmer's Model for x86 Multiprocessors"
date:   2023-09-14 12:13:00 -0600
categories: multicore computing, hpc, paper review
custom_excerpt: "Proposes x86-TSO, a mathematically rigorous yet accessible programmer's memory model for x86 processors. Addresses issues in previous Intel and AMD specifications."
---
# x86-TSO: a rigorous and usable programmer's model for x86 multiprocessors.
[x86-TSO: a rigorous and usable programmer's model for x86 multiprocessors.](http://www.spinroot.com/spin/Doc/course/x86_tso.pdf) Peter Sewell, Susmit Sarkar, Scott Owens, Francesco Zappa Nardelli, and Magnus O. Myreen. Communications of the ACM 53, 7 (July 2010), 89-97. DOI=10.1145/1785414.1785443 http://doi.acm.org/10.1145/1785414.1785443

## Paper Summary

Motivated by unreliable processor specifications and unpredictable memory behaviour, the authors propose a programmer's memory model of the x86 processor, x86-TSO, in which they describe the processor behaviour with more mathematical rigour, whilst still keeping the language accessible to all. The paper touches upon the issues in previous manuals published by Intel and AMD and provides a few examples where the expected behaviour does not match actual behaviour due to linguistic ambiguities or misses. The next section offers the actual model in two styles: an abstract machine model and an axiomatic model.

## Strengths

The x86-TSO provides a crisp, easy to understand memory model which is easier to reason with for a developer.
## Weaknesses

Analysis of the problem seems quite superficial as there are no lessons learnt or insights on why the problem was so prevalent.
Similarly, the reasoning behind several choices made while designing the x86-TSO are not clearly explained, making it harder to transfer the learnings to other processors (although related work is referenced). 
## Open issues

There may be corner cases where x86-TSO allows final states that are not allowed in practice, so more approaches testing might reveal useful information for clarifying the model further.

## Related Readings
* Chapter 4: Total Store Order and the x86 Memory Model; Chapter 5: Relaxed Memory Consistency. [A Primer on Memory Consistency and Cache Coherence](http://www.morganclaypool.com/doi/pdf/10.2200/S00346ED1V01Y201104CAC016) Daniel J. Sorin, Mark D. Hill, David A. Wood Synthesis Lectures on Computer Architecture. Morgan Claypool. 2011.