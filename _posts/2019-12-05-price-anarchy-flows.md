---
layout: post
title: Price of anarchy for dynamic flows
redirect_from: "/2019/12/05/price-anarchy-flows/"
permalink: price-anarchy-flows
---

This post is about flows from a game theory perspective. 
It originates from a recent talk of 
[Tim Oosterwijk](https://sites.google.com/view/timoosterwijk/home) at 
the University of Chile about 
[this paper](https://drive.google.com/file/d/1u-NUQLppaTDdNUUh-BvsXYJ2QH9RM1K9/view).

## A model for dynamic flows

We use a model useful to study settings like urban traffic.
The flow is dynamic (that is we do not focus on 
some stationary state) and there 
can be congestion. It is called the *fluid queueing 
model*.

The network is a graph, and there is one source node where the flow 
enters and one target node where the flow exits. Each edge of the 
network has a delay and a capacity per time unit. 
If more flows enters the edge than the capacity, a (FIFO) queue will 
form inside this edge. 

Maybe a good example is a network where on every edge there is a 
toll. If there is no queue, going through a toll $t$ takes some $s_t$ seconds,
and at most some $c_t$ cars can go through the toll at each second. 
If too many cars arrive, then a queue is forming, that will disappear 
later if not so many cars arrive.

## Objective

We consider a setting where a constant flow $u_0$ 
enters the network at each unit of time. 

Now at each intersection of degree $d$ a particule of flow can go in 
either of the $d-1$ directions. Given the choice of each particule at 
each intersection, the flow is completely defined, and you can measure 
how fast it is. For example routing every particule through the same edge
of small capacity would in general form a huge queue in this edge and 
make the flow very slow. 

We can consider at least two notions of efficiency: (1) for a given 
time, how much flow exits the network, and (2) for a given amount of flow 
to start with, when does the last particule exits the network. 
We we will consider the second one, called the *makespan*. 

## Price of anarchy

We study the makespan of different strategies for routing the flow.
As often in 
[algorithmic game theory](https://en.wikipedia.org/wiki/Algorithmic_game_theory),
one is interested in the [price of anarchy](https://en.wikipedia.org/wiki/Price_of_anarchy).
On a given instance this price is the ratio of the makespan of the best 
routing strategy divided by the makespan of the strategy where every 
particule optimizes its own travel time. 
In other words, the ratio between the strategy where an oracle decides 
optimally a route for every car, and the strategy where every driver 
optimizes its own travel time. Note that the setting where we let the 
particules (or drivers) decide is a kind of game, and we look at the 
equilibrium of this game. This might be called the *selfish* solution.

The price of anarchy of the problem is the largest 
(the supremum to be precise) price of anarchy among every instance of 
the problem.

## Result

Tim and his co-authors show (among other results) an upper bound of 
$e/(e-1)$ on the price of anarchy for this problem, under some conditions.  

## A key open problem: the monotonicity conjecture

There is a very neat and puzzling conjecture that, if true, would imply 
that the upper bound above always hold.

The so-called *monotonicity conjecture* states that: if one reduces the 
flow that enters in the network by unit of time (but keeping the total 
amount to push in the network),  then the makespan of the selfish solution 
increases.   

This seems very natural, but it is still open, and sometimes unexpected
things happen in the such games (like in 
[Braess's paradox](https://en.wikipedia.org/wiki/Braess%27s_paradox))

 




