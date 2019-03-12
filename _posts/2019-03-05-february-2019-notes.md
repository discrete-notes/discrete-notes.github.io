---
layout: post
title: February notes
redirect_from: "/2019/01/xx/february-2019-notes/"
permalink: february-2019-notes
---

Notes for February 2019.

---

![](assets/lierre.png){: .center-image height="450px"}

---

## Minorities in network

I attended a talk about minorities in network,
by [Claudia Wagner](http://claudiawagner.info/) at the 
[Complex network seminar](http://www.complexnetworks.fr/events/) of Sorbonnes 
University. 
There was a lot of content, here are a few things I noted. 

* Contrary to what I thought, a [$k$-core](https://en.wikipedia.org/wiki/K-core) 
is not another name for a $k$-clique. 
A $k$-core of a graph is a maximal connected subgraph where all the nodes have 
degree at least $k$. It can have much more nodes than just $k$
(a $k$-regular graph is its own $k$-core). Such subgraphs can be considered as 
coherent communities in social networks. 

* A part of the talk was about minorities in wikipedia. 
One would like to consider statements such as "women are more 
linked to other women than to men". 
This is not true in general because there are more men pages, thus 
links have more chance to point to men, but could still be true, proportionally.
But it's a bit too rough to just look at proportions because the graph may be 
complicated and there might be many correlations going on.
One way to deal with this is following: consider the graph of wikipedia 
bibliographies, note the global gender proportions, then erase the gender of the 
nodes, and reassign them at random, keeping the right proportions. 
Now you can compare the neighbourhoods in this new graph and in the original 
graph, and try to understand what's going on. One paper on the topic is the following: 
[It's a Man's Wikipedia? Assessing Gender Inequality in an Online Encyclopedia](https://arxiv.org/pdf/1501.06307.pdf)

* A notion known as *Burt efficiency*, or *brokerage*, or 
*[structural hole](https://en.wikipedia.org/wiki/Structural_holes)*, is more or 
less the following. 
A node that belongs to (or is close to) two clusters in a 
network, can have an advantage over the other nodes,
because it can enjoy the information gathered by both communities, and 
can choose to transfer or not such information. 
One can define coefficients to measure if a node is or not in such a 
position. 


## Multi-stage optimization

For dynamic algorithms, one is usually concerned with having a good solution
 at any time, but these solutions do not need to be related.
Multi-stage optimization, introduced in 
[this paper](https://arxiv.org/abs/1404.3768), considers the cases where one 
should not change the solution too much between the two steps. 
In other words, in this framework one maximizes the quality of the solution, 
while minimizing the churn. 

[I stumble on the notion in [this preprint](https://arxiv.org/abs/1901.11260).] 


## 1-2-3 Conjecture

Another edition of the Complex Network seminar by 
[Mohammed Senhaji](http://www.labri.fr/index.php?n=Annuaires.Profile&id=Senhaji_ID1441185629) 
(that I couldn't attend) was about the 1-2-3 conjecture, which is the following.

In any graph, one can label the edges with label 1, 2, or 3, such that, when each node 
computes the sum of the labels of its adjacent labels, not two neighbours have 
the same sum.

A survey about the conjecture is [here](https://arxiv.org/pdf/1211.5122.pdf).

## Lovász's new book
[László Lovász](https://fr.wikipedia.org/wiki/L%C3%A1szl%C3%B3_Lov%C3%A1sz) 
wrote a new book: 
[Graphs and geometry](http://web.cs.elte.hu/~lovasz/bookxx/geombook2019-01-20.pdf).


## Vandermonde identity

Vandermonde's identity is the following:

$$
\binom{m+n}{r} = \sum_{k=0}^{r}\binom{m}{k} \binom{n}{r-k}.
$$

I thought it was only a bachelor exercise, until it naturally popped up in the 
calculation in [a recent paper](https://arxiv.org/pdf/1812.09120.pdf).


