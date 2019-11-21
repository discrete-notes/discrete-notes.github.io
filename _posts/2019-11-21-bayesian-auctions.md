---
layout: post
title: Bayesian mechanism design and Yao's principle 
redirect_from: "/2019/11/21/bayesian-auctions/"
permalink: bayesian-auctions
---

I attended a talk yesterday about 
[algorithmic game theory](https://en.wikipedia.org/wiki/Algorithmic_game_theory) by 
[Alexandros Tsigonias-Dimitriadis](https://www.or.tum.de/en/group/alexandrostsigonias/)
as part of Santiago's [AGCO seminar](http://www.dii.uchile.cl/acgo/seminar-acgo/).
Here are a few elements from this talk.

## Basic Bayesian auction

The very basic setting we are looking at is the following: a client (the bidder)
comes to a seller (the auctioneer) with the goal of buying a particular item. 
The auctioneer has to set a price for the item. 
The bidder knows the maximum price at which she will buy the object (the value 
of the item for her).
If the auctioneer's price is higher than the bidder's value, the bidder does not 
buy the item, and if the price is lower then the bidder buys it, but the 
auctioneer "looses" the difference. 

In the [Bayesian setting](https://en.wikipedia.org/wiki/Bayesian-optimal_mechanism), 
the bidder's value is taken following a probability 
distribution, and the auctioneer knows this distribution. 
Then, the expected revenue of the auctioneer is the price she announces, 
multiplied by the probability that this price is lower than the value taken by 
the bidder. In other words, if $F$ is the cumulative probability distribution 
of the value of the bidder, 
then the expected revenue for a price $p$ is $p \cdot (1-F(p))$.
Then the auctioneer chooses a price $p$ that maximizes this quantity.

## Generalizations

One can generalize this to work with several bidders. This is called 
[Myerson mechanism](https://en.wikipedia.org/wiki/Bayesian-optimal_mechanism#The_Myerson_mechanism).

The paper of Alexandros and his co-authors 
([Robust Revenue Maximization Under Minimal Statistical Information](https://arxiv.org/abs/1907.04220)),
explores the setting where the auctioneer does not know the full distributions 
of the bidders, but only the means and the standard deviations. (That's why it 
is called *robust* revenue maximization.)

An important element of their proof is a generalization of Yao's minimax principle.

## Algorithmic minimax principle

[Yao's minimax principle](https://en.wikipedia.org/wiki/Yao%27s_principle) 
is a general theorem for randomized algorithms. 
Basically it is saying that the best randomized algorithm on its worst instance 
will get the same performance as the best deterministic algorithm on the worst 
distribution of instances. (This needs a precise statement, to say which thing is 
optimized first etc.).

In the context of Alexandros, the instances are distributions (of which we know
only the mean and the standard variation) thus a distribution of instances is 
a distribution of distributions. This can be made precise, by considering a
mixture of distributions. 

  


