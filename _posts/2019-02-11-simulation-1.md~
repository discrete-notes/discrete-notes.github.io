---
layout: post
title: Simulation argument I. General technique
redirect_from: "/2019/02/11/"
permalink: simulation-1
---

---

---

As.
[said earlier](https://discrete-notes.github.io/january-2019-notes) 
on this blog, a 
[recent preprint](https://arxiv.org/abs/1901.02441) 
proves a set of long-expected lower bounds for distributed graph algorithms. 
This post is the first of a (short) series of (short) posts about the basics of 
this paper. 

## A series of posts

In this first post we give an overview of the *simulation argument*, which is 
the framework used for the lower bound. 

The next posts will be about: 

* specific construction for edge labelings on bicolored trees
* Example 1: sinkless orientation
* Example 2: maximal matching

Most of the content of this series is probably better explained in the 
preprint cited above, so you may want to look at it instead of these posts! 
The main difference will appear in the second post where I propose a slightly 
different vocabulary, based on polynomials. The posts assume familiarity with 
the local model.

### A few bits of context 

The simulation technique can be traced back to Linial, 
and his $\Omega(\log^*n)$ lower bound for coloring.[^1]
However, it did a come-back with 
[a 2015 paper](https://arxiv.org/pdf/1511.00900.pdf) that had a different point 
of view. 
It was then simplified and improved.[^2] 
The technique was an important part of 
[the talk of Juho Hirvonen](http://adga.hiit.fi/2017/hirvonen.pdf) 
at the 
[2017 ADGA workshop](http://adga.hiit.fi/2017/). 

## Overview of the simulation argument

The core question of the simulation argument is the following. 
Suppose that in time $T$ you can solve a problem. Then what can you solve 
if you have only $T-1$ rounds? 
For lower bounds, the basic line of reasoning is the following. 

### Base step: 0 rounds
Fix a problem $P$.
Suppose you have a way to do the following transformation.

*Transformation:*  
Start with:  
an algorithm $A$ in $T$ rounds for a problem $P$.   
change it into:  
an algorithm $A'$ in $T-1$ rounds for another problem $P'$.   

Then, say you want to prove that solving $P$ requires more than 1 
round. 
Then you only need to prove that you have a transformation as above, with $T=1$, 
and that $P'$ is not trivial (that is, to prove that 
$P'$ cannot be solved in zero round) 
Indeed if there is an algorithm in 1 round for $P$, then you can transform it 
into an algorithm in 0 round for $P'$, which would contradict the 
non-triviality of $P'$. 
Then you known that $P$ requires at least 2 rounds. 
This may sound silly as we have just moved the problem: now you are left 
with proving that $P'$ is non-trivial. But this is usually much simpler.  

### Induction
Now, you want to prove lower bounds above one round, say $k+1$ rounds. 
The argument goes the following way.
For the sake of contradiction, suppose there is an algorithm in $k$ rounds for 
your problem $P$.
Now you prove that there exists a family of problems $P_0, P_1, P_2, ...,P_k$, with 
$P_0=P$, such that: 

* none of them is trivial
* given an algorithm for $P_i$ in $k-i$ rounds, you can transform it into an 
algorithm in $k-i-1$ rounds for $P_{i+1}$. 

The last point implies that $P_k$ can be solved in $0$ rounds, which impossible 
because the first point states that it is non-trivial. 
Thus $P$ needs at least $k+1$ rounds.

### Simulation argument
The question now: how do you define a transformation?   
Suppose you know an algorithm in $T$ rounds, but you have only a view of 
$T-1$ rounds. Then you can do the following.

* Imagine all the possible ways your $T-1$ neighbourhood could be extended to a 
$T$ neighbourhood. 
* Compute a solution for each of these extensions, using you $T$-round algorithm.
* Label you node/edges with the set of all the labels that the T-round algorithm
would use in one of the extensions.
 
Obviously you are not solving the original problem because you are labeling your
node/edges with sets of labels, instead of labeling them with only one label. 
Also this labeling may be uninteresting: every node/edge could be labeled with 
all the possible labels. 
But maybe it *is* interesting. 
And then you may be able to define a non-trivial problem $P'$ 
(probably a quite artificial problem but it's ok) such that this set-labeling 
is a proper labeling for $P'$. 

### Simplification step
You may also want to have a simplification step. 
This is a step that you perform after you have labeled your nodes/edges with 
sets of labels.
The goal is to simplify the proof, by replacing the sets of labels by something 
simpler, typically simple labels. For example you decide that every set of labels 
{$a,b$} is replaced by $a$. For this step to be useful you need that:
 
* one can compute teh simplification without further communication (e.g. no 
synchronization with neighbours)
* the new labels fit into a language that has good properties, in particular, it 
is not trivial.

### Footnote

[^1]: The simulation argument appears more clearly in the [modern version of the proof](https://users.ics.aalto.fi/suomela/doc/linial-easy.pdf)

[^2]: There is an soon coming note by [Sebastian Brandt](https://disco.ethz.ch/alumni/brandts) that formalizes precisely the approach.

