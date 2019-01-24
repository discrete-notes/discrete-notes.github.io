---
layout: post
title: October batch, forgotten notions
redirect_from: "/2019/01/24/"
permalink: october-batch-forgoazfafazfs
---

I saw many talks in October and I plan to blog a bit about those in some 
posts to come. This first post is about some notions a somehow knew but couldn't 
really define.

## $\epsilon$-nets
 
[$\epsilon$-nets](https://en.wikipedia.org/wiki/%CE%95-net_(computational_geometry)) 
are often appear in computational geometry. Consider a set of points $X$ in 
a geometric space, and a collection $C$ of subsets of $X$ (for example you have 
a collection of balls, then it defines the collection of subsets of $X$: the 
points contained in each ball). 
Now you are given an $\epsilon\in [0,1]$. 
An $\epsilon$-net $E$ is a subset of $X$, such that for every element $c$ of $C$ 
that is large enough, $c$ contains an element of $X$, and large enough means: 
$$\frac{|c|}{|X|}\geq \epsilon.$$ 

As one can imagine this is a useful tool to build approximation algorithm, as 
one may be able to focus on the net, that is hopefully much smaller than $X$. 

The concept is related to the 
[VC dimension](https://en.wikipedia.org/wiki/Vapnik%E2%80%93Chervonenkis_dimension).

A nice introduction with a chocolate-consumer example can be found 
[here](https://www.ti.inf.ethz.ch/ew/lehre/CG12/lecture/Chapter%2015.pdf).

## PTAS, QPTAS etc.

A small list of the accronyms for approximation schemes (PTAS is fine for me, 
but after that...):

* [PTAS](https://en.wikipedia.org/wiki/Polynomial-time_approximation_scheme), 
polynomial-time approximation scheme: for every $\epsilon$, you get 
approximation $(1+\epsilon)$, in polynomial time. That is when you fix 
$\epsilon$ you get a polynomial in $n$. Typically you have time complexity 
$f(\epsilon)\times n^{g(\epsilon)}$, 
where $f$ and $g$ can be arbitrarily bad.
* EPTAS, for efficient-PTAS: here the exponent should not depend on $\epsilon$. 
With the example above, $g$ is a constant, and $f$ can still be arbitrary.
* FPTAS, for fully-PTAS: the algorithm is polynomial in both $n$ and $1/\epsilon$.
Typically, $g$ is a constant, and $f$ a polynomial in $1/\epsilon$.
* QPTAS, quasi-polynomial-time approximation scheme: this is worse than PTAS, 
because you allow that even for a fixed $\epsilon$ the complexity is only
quasi-polynomial, for example some $n^{\log n}$.
* PRAS, EPRAS, FPRAS: the same as PTAS, EPTAS, FPTAS, but randomized (the result 
has to be a correct approximation with high probability).

(Both this section and the previous one originate from the talk of 
[Edouard Bonnet](https://www.lamsade.dauphine.fr/~bonnet/) for the paper 
*[EPTAS for Max Clique on Disks and Unit Balls](http://ieee-focs.org/FOCS-2018-Papers/pdfs/59f568.pdf)* 
at FOCS 2018.)

## Doubling dimension

A lot of recent papers prove nice results in doubling metrics. The [doubling 
dimension](https://en.wikipedia.org/wiki/Doubling_space) 
of a metric space is the smallest positive $k$ such that every ball of 
the space can be covered by $2^k$ balls of half the radius. You can think of 
the plane, and show that you can cover a ball of radius 1, with 7 balls of 
radius 1/2, which gives doubling dimension 3. More generally for the euclidian 
space $R^d$, the doubling dimension is known to be in $O(d)$. Thus bounded 
doubling dimension is a natural generalization of bounded dimension.

(The notion appears for example in *[$ε$-Coresets for Clustering (with Outliers) 
in Doubling Metrics](http://ieee-focs.org/FOCS-2018-Papers/pdfs/59f814.pdf)* also 
presented at FOCS.)





