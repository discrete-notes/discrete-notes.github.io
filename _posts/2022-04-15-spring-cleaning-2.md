---
layout: post
title: Spring notes (2)
redirect_from: "/2022/04/15/spring-cleaning-2/"
permalink: spring-cleaning-2
---

A few more notes to empty the stack.

Picture: TBA.


## Odds algorithm

The [odds algorithm](https://en.wikipedia.org/wiki/Odds_algorithm) is a 
general method for 
[optimal-stopping problems](https://en.wikipedia.org/wiki/Optimal_stopping), 
such as the [secretary problem](https://en.wikipedia.org/wiki/Secretary_problem).

The setting is the following:

* Let $n$ an integer, and $p_k$, for $k=1,..,n$ be $n$ numbers in $(0,1]$.
* A sequence of bits $s=(s_k)_k$ is created by drawing each $s_k$ 
independently at random with $P(s_k=1)=p_k$.
* The player sees the elements of $s$ one after the other, and should stop 
on the last 1. 

An example of application is for auctions, where $p_k$ represents the 
fact that the k-th bid is higher than all the bids that appeared before.

Let's start with some notations.
Let the *odd of position $k$* be $r_k=\frac{p_k}{1-p_k}$. 
For every $t\in [1,n]$ Let $R_t=r_n + r_{n-1}+...+r_{t}$.
Consider the first $t$ such that $R_t> 1$, and call it $t^*$. 
(I the sum does not reach $1$, set $t^*=1$.)

The odds algorithm is: stop as soon as you see a 1 at a position of 
index $t^*$ or larger.

This algorithm happens to be optimal!

## Order of the authors names

There has been recently efforts in the TCS community to reduce bias 
originating from the way we cite the authors of papers. Basically, the 
current system has a positive bias for people whose names appear early in 
the alphabet. Now there are several questions:
 
Is it really a things?
I haven't seen any statistics about TCS or even maths, but I saw some stats
in economics (where they also use alphabetical order), and it is 
quite clear that there is non-negligible bias (check [this blog post] 
for more about this). The studies look serious, controlling the other 
possible factors (e.g. discrimination based on ethnicity etc.).

Where does it come from?
The most plausible explanation is that this comes from the habit of citing 
papers by the name of the first author (either informally in discussions, 
or formally with "et al."). Knowing a name better than another introduces 
a bias (e.g. when thinking about speakers for invited talks, or just 
reviewing papers). At first it seems like a weak effect, but given the 
amount of money spent by companies on advertising for exactly this purpose, 
we probably underestimate it.

What are possible fixes? 
Call for papers of conferences 
(e.g. [STOC 2022](http://acm-stoc.org/stoc2022/cfp.html)) have taken into 
account this phenomenon in several ways. One is to ask to avoid the "et al."
formulation. Another is to allow for randomized name ordering. In order to 
avoid confusion between randomized and ranked orderings, the notation ⓡ has 
been allowed (Author-random1 ⓡ Author-random2 ⓡ etc.). This should 
appear in both the paper and the future citations of the paper. 
It is arguably uglier than commas, but I think it is worth it. 

## Links

* David Eppstein has a list of 
[21 proofs of Euler formula](https://www.ics.uci.edu/~eppstein/junkyard/euler/).
Hopefully, I'll find some time to write on this blog about my favorite proofs.

* An [excellent video](https://www.youtube.com/watch?v=ahW96yYmWx0) by Ryan 
O'Donnell about the [switching lemma](https://en.wikipedia.org/wiki/Switching_lemma)
(both fun and very enlightening). 

* The [bulletin of EATCS](http://bulletin.eatcs.org/index.php/beatcs) has 
some new interesting columns: "Know the people behind the papers" that is 
an interview of a well-known researcher (Keren Censor-Hillel in the current 
issue, and Kurt Melhorn for the previous one), and "The Theory Blogs Column"
managed by Luca Trevisan, about TCS blogs (the first one is *Computational 
complexity* by Lance Fortnow).

* If you work with graphs in [SageMath](https://www.sagemath.org/), then 
you should take a look at 
[Phitigra](https://github.com/jfraymond/phitigra/blob/master/README.md), a 
graph editor created by [Jean-Florent Raymond](https://perso.limos.fr/~jfraymon/).

* At some point I have been looking for a linux-compatible presentation viewer 
that would show some additional information on the presenter laptop (next 
slide, remaining time, etc.). It seems that [pdfpc](https://pdfpc.github.io/) is an 
option, but I haven't tried it yet.
