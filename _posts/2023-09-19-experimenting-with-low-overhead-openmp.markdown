---
layout: post
title:  "Paper Review: Experimenting with Low-Overhead OpenMP Runtime on BG/Q"
date:   2023-09-19 12:35:00 -0600
categories: multicore computing, hpc, paper review
custom_excerpt: "Proposes optimizations to OpenMP for better scalability on BlueGene/Q by caching thread group allocations. Achieves up to 4.9x improvement in overhead reduction for 64 threads."
---

# Experimenting with Low-Overhead OpenMP Runtime on BG/Q
Experimenting with low-overhead OpenMP runtime on IBM Blue Gene/Q. Download Experimenting with low-overhead OpenMP runtime on IBM Blue Gene/Q.A. E. Eichenberger and K. O'Brien. IBM J. Res. Dev. 57, 1 (January 2013), 91-98. DOI=10.1147/JRD.2012.2228769 

## Summary

This paper proposes optimisations to the OpenMP specification to make it more scalable for systems such as the BlueGene/Q supercomputer which have a high number of available threads. The major problem that the authors try to solve is the overhead from continuous allocation/de-allocation of thread groups to tasks. The key observation here was that majority of the allocations required repetitively searching for the same few thread configurations and allocating them. The proposed methods involve caching thread group allocations to get near-constant time allocation, followed by removing work description assignment notifications, adding bit-vector "go-ahead" signalling which provide major benefits, and a few improvements to the OpenMP API which had minor effects. The results show improvements of 1.9, 2.7, and 4.9x, compared to the original overheads for team sizes of, respectively, 4, 16, ands 64 threads.

## Strengths

The paper presents clear, easy to implement changes with good results.
## Weaknesses

The key observation that thread allocation is repetitive seems to come from previous experiments, however the associated results for this are not included.
## Problem / Open issues

Potential trade-offs, downsides, corner-cases by making said optimisations are not explored, e.g. the additional caching would involve using more memory.
The experiment is done with 4 threads per core, but it could be interesting to see how it works with multicore processors with higher thread counts.
The results vary quite a bit over the size of threads group, so it would be helpful to analyse frequency of encountering different thread groups over some set of applications in order to understand the broad impact of these optimisations.

## Related Reading
* [The Design of OpenMP Tasks](https://ieeexplore.ieee.org/stamp/stamp.jsp?arnumber=4553700&casa_token=YZuvhnfS74QAAAAA:ygooO78LwMDJOIgONDhFkcw1xqbEY9hnSqk6Ds95YlS_yq_ybXShlozlK9ab2oyxpGFyrPeAKw). Eduard Ayguadé, Nawal Copty, Alejandro Duran, Jay Hoeflinger, Yuan Lin, Federico Massaioli, Xavier Teruel, Priya Unnikrishnan, and Guansong Zhang. IEEE Trans. Parallel Distrib. Syst. 20, 3 (March 2009), 404–418.  https://doi.org/10.1109/TPDS.2008.105