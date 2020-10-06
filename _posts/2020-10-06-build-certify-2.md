---
layout: post
title: Can we always build and certify at the same time? (MST with fragements)
redirect_from: "/2020/10/06/build-certify-2/"
permalink: build-certify-2
---   

This is the second post of a series about self-stabilization. Many 
self-stabilizing algorithms build and certify a solution at the same 
time, and the main question of this series is whether this is always 
possible if one insists on space and time efficiency. 

In this post, we will describe the classic way to build a minimum 
spanning tree (MST) by merging fragments. Then, we will see the classic
cettification of MST based on this construction. In the next post we 
will finally discuss the question above.  

![](assets/arbre-fragment.png){: .center-image width="80%"} 

## Building an MST with fragments

The classic way to build a minimum spanning tree (MST), is to use 
so-called *fragments*. This technique originates from 
[Borůvka's algorithm](https://en.wikipedia.org/wiki/Bor%C5%AFvka%27s_algorithm) 
and is used in the celebrated 
[GHS algorithm](https://en.wikipedia.org/wiki/Distributed_minimum_spanning_tree#GHS_algorithm).
We will describe this approach on the following weighted graph.

![](assets/MST-1.png){: .center-image width="90%"} 

The general method is the following.
We will select edges little by little.
The idea is that at any point of the algorithms, there are *fragments*, 
which are sets of nodes, such that they are connected by a spanning 
tree of selected edges. At the beginning, every node is its own fragment.
When a new edge is selected, the two fragments of the two endpoints 
merge, that is, the two sets of nodes merge into one set, and the two 
spanning trees are connected into one spanning tree. At the end of the 
computation there is only one fragment, with one spanning tree, and 
this spanning tree has minimum weight.

Now let's get into the details with our example. (For simplicity, we do 
not rewrite all the weigths on all the pictures.) First, every node 
chooses the lightest among its adjacent edges. 

![](assets/MST-2.png){: .center-image width="90%"}

For now, we consider only the case where the edge weights are distinct, 
like in our example.
Then there is no choice for the nodes, and all 
the edges that have been chosen by at least one node are selected.
The set of selected edges forms a forest, and each tree of this forest 
is a fragment.

![](assets/MST-3.png){: .center-image width="90%"} 

(In the picture above, the non-selected edges between nodes of a 
fragments are more transparent, because they will not be useful anymore.)

So now for the second phase, every fragment choses the *lightest 
out-going edge* that is the lightest among all edges that have exactly 
one extremity in the fragment.  

![](assets/MST-4.png){: .center-image width="90%"} 

And again, we merge the corresponding fragments by selecting the chosen
edges. 

![](assets/MST-5.png){: .center-image width="90%"} 

The last phase is the one where the last fragments get merged.

![](assets/MST-6.png){: .center-image width="90%"} 

And we get the final tree, which is a minimum spanning tree.

![](assets/MST-7.png){: .center-image width="90%"} 

## Properties

Here are a few comments about this process. We will reuse some of these
properties in a later post.

* Here we have assumed that the weights are distinct, but in general 
this is not the case. If not then we need an extra step, where the nodes
having two outgoing edges with the same weight decide which one will be 
selected.

* The process is incremental: the edges that have been added in an early 
phase are kept during the whole computation and appear in the final
MST.

* There are at most $O(\log n)$ phases, because the number of fragments 
is at least halved at each phase.

* In the process, the merging is quite uncontrolled: it could be that a
fragments merges with just one other fragments (like in the two last 
phases in the example), but it can also be two (like in the first 
phase, in the middle and on the left), or actually $Theta(n)$.

* Also the place where the fragment merge is uncontrolled: a fragment 
can be merging with one fragment in some places and with another 
fragment very far away. 

## MST certification

It is possible to certify a MST by basically describing the key pieces 
of the process above. This scheme uses certificates of $O(\log^2n)$ bits
which is very good, although not optimal for every weight range. 

We will describe these labels quickly, using the same example as above. 
In particular we will focus on the node named $I$ in the following 
drawing.

![](assets/MST-certificates-1.png){: .center-image width="80%"} 

For this node, the important steps are: the merge with $J$, then the 
merge with of the fragment $[I,J]$ with the fragment $[F,H]$, and then 
the merge of $[I,J,F,H]$ with $[A,B,C,D,E,G]$.

![](assets/MST-certificates-2.png){: .center-image width="80%"}

This translate into the following certificate for $I$:

![](assets/MST-certificates-3.png){: .center-image width="80%"}
 
In addition to the number of the phase, and the characteristics of the 
merging edge, the node is given the name its "parent" in a spanning tree
 of the fragment pointing towards the merge edge and the distance to 
 the merge edge. These two last pieces of information are necessary to 
 certify the existence of a merge edge. 

