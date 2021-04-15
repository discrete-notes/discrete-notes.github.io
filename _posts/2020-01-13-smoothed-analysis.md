---
layout: post
title: Smoothed analysis in distributed computing
redirect_from: "/2020/01/13/smoothed-analysis/"
permalink: smoothed-analysis
---

Happy 2020! A short post about smoothed analysis in distributed 
computing.


![](../assets/arbre-patagonie.jpg){: .center-image width="70%"}
<p align="center"><small><i>
Some (non-minimum-spanning) trees.
</i></small></p>


[Smoothed analysis](https://en.wikipedia.org/wiki/Smoothed_analysis) is 
about a complexity measure in between the complexity on random instances 
and the complexity on worst-case instances. 
It basically asks about the complexity on the worst instance,
but with a small random permutation.
The goal of this measure is to better capture the complexity observed in
practice.

For example, the 
[simplex algorithm](https://en.wikipedia.org/wiki/Simplex_algorithm)
performs very well in practice
but is proved to be exponential in the worst-case. This means
that worst-case complexity is not the right tool to evaluate this algorithm.
But if you consider a bit of noise, then the simplex algorithm becomes 
polynomial! More precisely the complexity is bounded 
by a polynomial in $n$ and $1/\sigma$, where $\sigma$ is the standard 
deviation of the gaussian noise. This somehow explains why the simplex 
is so good in practice: the examples where it is exponential are very 
special constructions, that are eliminated by small perturbations.

I was recentely asked whether there exists some smoothed analysis 
in network distributed computing. There is actually a 
[recent paper](https://arxiv.org/pdf/1911.02628.pdf) that started that. 
It does a smoothed analysis of distributed minimum 
spanning tree. 

A problem with smoothed analysis, or a feature maybe, is that it can be 
made in different ways, in particular a question is: What kind of noise 
do you consider? When there are 
numerical inputs, you can modify these inputs with a gaussian noise. But 
in the case of minimum spanning tree, small perturbations of the weights
do not change much.
More precisely, given a difficult instance, one 
would have to add a noise of the same order of magnitude as the 
weights to break the lower bound. 
Instead, the authors of the paper above consider a model 
where each node is allowed to ask for a new adjacent random edge at 
each round. These new edges have infinite weight thus they are not 
useful for the MST, only for the communication. 
This seems a rather strange model, but I can imagine that a lot of more
natural variants do not make sense. 
 
More generally, a problem I can see with smoothed 
analysis for the LOCAL model for example, is that it is based on the 
idea that random instances are easy. 
For graphs, a natural choice of random instances, is 
[Erdos-Renyi graphs](https://en.wikipedia.org/wiki/Erd%C5%91s%E2%80%93R%C3%A9nyi_model),
but these are not always easy for distributed algorithms: they are 
sometimes used as lower bound instances (or more precisely they are 
expanders,  and have logarithmic girth, which are two properties that 
often pop up in lower bounds). 
Some graphs that are somehow easy are grids, but I don't know what kind of 
random transformation you can apply to a graph to make it more grid-like. 

One could also play with the identifiers. For example a random identifier 
assignment often boils down to a randomized algorithms
(see [this](https://arxiv.org/abs/1704.05739)), and maybe some slightly 
random assignement could make sense. 
