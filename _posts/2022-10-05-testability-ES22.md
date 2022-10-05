---
layout: post
title: Quick read&#58; Testability and local certification of monotone properties
in minor-closed classes
redirect_from: "/2022/10/05/testability-ES22/"
permalink: testability-ES22
---

Hi! To start this new academic year, I'm experimenting a different format. 
I skimmed through a paper I was curious about, and this post is a very 
short summary of the context and results. 
The paper is: *Testability and local certification of monotone properties 
in minor-closed classes* ([arxiv page](https://arxiv.org/abs/2202.00543), 
[ICALP version](https://drops.dagstuhl.de/opus/volltexte/2022/16399/)), 
by [Louis Esperet](https://oc.g-scop.grenoble-inp.fr/esperet/) and 
[Sergey Norin](https://www.math.mcgill.ca/snorin/).


## Property testing

The paper is about 
[property testing](https://en.wikipedia.org/wiki/Property_testing) 
and local certification of graph properties. 
I'll start with a few definition for the testing part. 

In the following, for concreteness, one can think of planarity as the 
property we look at. 
A graph $G$ is $\epsilon$-far from a property $P$ if one needs to modify 
at least $\epsilon |E(G)|$ adjacencies (e.g. replacing edges by non-edges 
or vice-versa) to get a graph having property $P$. 
In property testing we are interested in the question of how much we need
to know about the graph to be able to decide whether a graph satisfies 
property $P$ or is $\epsilon$-far from it. 
Since we are not going to know 
the entire graph, it is usually impossible to have exact answers, which is 
why we don't try to answer correctly for graphs that are very close to 
having the property (which are likely to be false positive).

There are various ways to query the graph to gain information about it, but 
in this paper the model is the *random neighbor oracle*. 
In this model, a 
query can either ask to reveal a random vertex, or a random 
neighbor of a vertex that has already been revealed. This is similar to 
what is called the *sparse model*. 

We are interested in the question: what can be tested with a constant 
number of such queries? 
In the other words, for which property $P$ can we design 
an algorithm (the tester) that makes a constant number of random neighbor 
oracle queries and decides whether the graph has property $P$ 
or is $\epsilon$-far from it.
Note that by "constant" we mean that the number of queries does not grow with 
the size of the graph, but it does depend on $\epsilon$.
Such an algorithm will necessarily make mistakes and only randomized 
algorithms make sense. 
If the answer is always correct when the graph satisfies $P$ the tester has 
one-sided error, otherwise it has two-sided error. 

## H-free, monotone, minor-closed

Before giving the results of the paper we need a bit of graph theory 
vocabulary. 
A class of graphs is 
*[minor-closed](https://en.wikipedia.org/wiki/Graph_minor#Minor-closed_graph_families)* 
if it is stable by edge and vertex 
removals, and by 
[edge contractions](https://en.wikipedia.org/wiki/Edge_contraction).
[Robertson-Seymour theorem](https://en.wikipedia.org/wiki/Robertson%E2%80%93Seymour_theorem)
states that this is equivalent to say that the class is defined 
by a finite set of forbidden minors, that is, a finite set of graphs that 
cannot be obtained by edge and vertex removals, and by edge contractions.
(You can check that planar graphs are minor-closed, and the corresponding 
list of forbidden minors is $\{K_5,K_{3,3}\}$.)

A class of graphs is *monotone* if it is closed by taking subgraphs, that 
is, closed by edge and vertex removals. 
The equivalent of Robertson-Seymour theorem here would be "this is 
equivalent to having a finite set of forbidden subgraphs", but this is wrong. 
Consider the bipartite graphs. They are closed by subgraphs, but to define 
bipartite graphs via forbidden subgraphs one needs an *infinite* family of
subgraphs: all the cycles of odd length. 
Therefore there is another notion: for a finite family $\mathcal{H}$ of 
graphs, the $\mathcal{H}$-free graphs are the ones that do not have a graph
of $\mathcal{H}$ as a subgraph. 

Note that being $\mathcal{H}$-free for some $\mathcal{H}$ implies that the 
class is monotone, but not the reverse.

## Theorem

The main theorem of the paper is the following. 

**Theorem:** For every minor-closed class $\mathcal{G}$, and any monotone 
property $P$, one can test with one-sided error whether a graph in $\mathcal{G}$ 
has property $P$. 

Remember that we are in the setting with a constant number of random 
neighbor queries, and note that we restrict the input: instead of any graph, 
we promise that the input comes from a given minor-closed class.
(A minor technicality here: the class of all graph is minor-closed, but 
the theorem actually holds only for proper minor-closed classes, i.e. the ones 
that are not the set of all graphs.)

This results improves on a 
[previous result by Czumaj and Sohler](https://ieeexplore.ieee.org/document/8948636) 
that holds only for properties that are $\mathcal{H}$-free. 

## Approximate local certification

The techniques used to prove the theorem above can also be used to prove results 
about local certification. Defining local certification is a bit too long 
for this post so I will assume that the reader knows the concept. 
Otherwise, a reference is 
[this introduction to the topic](https://arxiv.org/abs/1910.12747) 
I wrote recently.

Actually, the result is about *approximate local certification*: if the graph 
has the property, then there is a certificate assignment that convinces all 
the nodes, and if the graph is $\epsilon$-far from the property, no 
certificate assignment can convince all the nodes. Note that nothing is 
randomized here.

To state the result we need one more graph definition: a graph class is 
*summable* if for any pair of graphs $G_1$, $G_2$ in the class, the 
disjoint union of $G_1$ and $G_2$ is also in the class.

**Theorem:** For any minor-closed class $\mathcal{G}$, and any monotone 
summable property $P$, it is possible to approximately certify the property
$P$ for the graphs of $\mathcal{G}$, with constant-size certificates (and 
constant-size view).

This improves on a 
[result by Elek](https://www.sciencedirect.com/science/article/abs/pii/S0097316522000516?via%3Dihub) 
that requires bounded degree, and it is actually generalized in the 
paper to graph of bounded asymptotic dimension instead of minor-closed graphs. 
(I hope to blog soon about asymptotic dimension.) Also, if one removes the 
summability assumption, then the same results holds but with logarithmic 
size certificates.




