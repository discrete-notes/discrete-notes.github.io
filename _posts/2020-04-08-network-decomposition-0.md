---
layout: post
title: Network decomposition&#58; Introduction
redirect_from: "/2020/04/08/network-decomposition-0/"
permalink: network-decomposition-0
---

This post is an introduction (and a table of contents) for a series of posts on
distributed network decomposition. 

![](assets/caravane-0.jpg){: .center-image width="90%"}


One of the important papers of these recent years in distributed graph 
algorithms will appear at STOC this summer:

"Polylogarithmic-Time Deterministic Network Decomposition and Distributed 
Derandomization" by [Václav Rozhoň](https://n.ethz.ch/~rozhonv/) and 
[Mohsen Ghaffari](https://people.inf.ethz.ch/gmohsen/) from ETH Zurich.

It is basically the description of a distributed algorithm that performs what is 
called a *network decomposition*, faster than before. This decomposition can 
then be used to do many other things fast, and the paper solves several important 
open problems of the field. 

I quickly looked at the paper when it appeared on arxiv, but I want to 
understand it better, and writing a series of posts about it is good way to do 
this. 

Here is the my current plan for this series:

1. *[Local algorithms](https://discrete-notes.github.io/network-decomposition-1-local-algorithms)*, 
an introduction to local algorithm, with the example of 
the maximal independent set problem.
2. *[Impact for distributed algorithms](https://discrete-notes.github.io/network-decomposition-2-impact)*, 
that is, why is a network decomposition so useful. 
3. *[Centralized construction](https://discrete-notes.github.io/network-decomposition-3-centralized)*, 
how to build a network decomposition with good parameters in a centralized manner.
4. *[Weak and strong decomposition](https://discrete-notes.github.io/network-decomposition-4-weak-strong/)*, 
some useful precisions about the decomposition
5. (and more) TBA 
