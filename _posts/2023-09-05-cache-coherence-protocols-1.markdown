---
layout: post
title:  "Paper Review: Cache Coherence Protocols - I"
date:   2023-09-05 13:15:00 -0600
categories: multicore computing, hpc, paper review
custom_excerpt: "Provides a comprehensive overview of cache coherence protocols, explaining controller networks and protocol structures. Details the key components: states, transactions, and protocol design options."
---

Cache Coherence Protocols
Chapter 6: Coherence Protocols;
Chapter 7 Snooping Coherence Protocols;
Chapter 8: Directory Coherence Protocols.
[A Primer on Memory Consistency and Cache Coherence](https://link.springer.com/book/10.1007/978-3-031-01764-3). Vijay Nagarajan, Daniel J. Sorin, Mark D. Hill, David A. Wood.  Synthesis Lectures on Computer Architecture. Morgan Claypool. 2020.

## Summary

In this chapter, a brief overview of cache coherence protocols is provided. First a top level view of the cache and memory controllers along with their basic functions is explained, followed by a closer look at what structure a coherence protocol imposes on this controller network. To illustrate these points, a simplified example is given. Finally, the chapter goes over the components that are defined by a coherence protocol, i.e. states, transactions and major protocol design options.

## Strengths:

The paper detangles the nuances of implementing coherence protocols to give a clear, generalised description of what it conceptually means.

## Weaknesses:

Could not identify one, as this is not a standalone paper.

> should have analyzed one of the snooping protocols and directory protocols or compared them (they are described in chapters 7 and 8)


## One problem / open issue:

The chapter mentions that coherence protocols can be "simplistic and inefficient" but do not elaborate on it.