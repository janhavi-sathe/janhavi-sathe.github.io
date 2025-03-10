---
layout: post
title:  "Paper Review: Cache Coherence Protocols - II"
date:   2023-09-05 13:15:00 -0600
categories: multicore computing, hpc, paper review
---

Victim Replication: Maximizing Capacity while Hiding Wire Delay in Tiled Chip Multiprocessors (http://pages.cs.wisc.edu/~isca2005/papers/06A-01.PDF), M. Zhang and K. Asanovic. In Proceedings 32nd International Symposium on Computer Architecture, Madison, WI, June 2005.

## Summary

This paper introduces a new cache management policy called "Victim Replication" as an extension of shared cache schemes. Victim Replication helps reduce on-chip communication delays. The results of the accompanying simulation show that victim caching can help reduce memory latency by 16% of L2 Shared scheme. 

## Strengths

The paper provides balanced evidence of when victim replication has an effect vs when it doesn't have as much effect.
## Weaknesses

Cannot point any glaring weaknesses...
## Problems / Open Issues

This paper introduces a new technique, the limits of the degree of its effects remain to be explored.

## Related Readings
* Elastic Cooperative Caching: An Autonomous Dynamically Adaptive Memory Hierarchy for Chip Multiprocessors. (http://people.ac.upc.edu/rcanal/pdf/Herrero-ISCA2010.pdf) Enric Herrero, Jose Gonzalez, Ramon Canal. International Symposium on Computer Architecture, Saint-Malo, France, June 2010.

## Notes by Dragana Grbic
should have analyzed the paper in more details:
1. there are weaknesses you could have addresses (etc. complexity of cache management policy, additional hardware support, more memory consumption due to replications etc.)
2. should have analyzed strengths in more details (etc. performance improvement in average memory access latency, reduce in on-chip communication delay etc.)