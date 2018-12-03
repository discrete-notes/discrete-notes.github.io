---
layout: post
title: November notes
redirect_from: "/2018/11/30/november-2018-notes/"
permalink: november-2018-notes
---

A few notes for November 2018.

---

## A new paper on descriptive complexity of distributed computing
[Descriptive complexity](https://en.wikipedia.org/wiki/Descriptive_complexity_theory) 
basically aims at characterizing complexity classes through logic. A classic 
results is [Fagin's Theorem](https://en.wikipedia.org/wiki/Descriptive_complexity_theory)
that characterize NP. 
Descriptive complexity for distributed computing is a relatively new topic,[^1]
and a [new paper](https://arxiv.org/abs/1811.08197) just came out on arxiv.
I'm not a specialist, but from what I understood, the usual assumption in the
LOCAL model that there are unique identifiers, is pretty difficult to transfer 
into logic, and this paper make a step in this direction.

## A map of the theory of distributed computing community 
[Jukka Suomela](https://users.ics.aalto.fi/suomela/) published
[a nice map](https://plus.google.com/+JukkaSuomela/posts/JgWYFk4XzWW) of the 
PODC/DISC (the two main conferences in theory of distributed computing) community.  
The nodes are the authors, that are linked by edges of different thickness, 
depending on how much they have collaborated, or have had papers in the same 
sessions. There are strong thematic clusters, which is no surprize.

## Symmetries in LPs and SOS
I attended the PhD defense of 
[Cécile Rottner](https://www.lip6.fr/actualite/personnes-fiche.php?ident=D1634)
who was a student in the OR team of [LIP6](https://www.lip6.fr/?LANG=en). 
Her thesis was about a problem that
any electric utility company faces: how to manage the different the power plants
to meet the demand while using the less energy possible, given that there are 
many constraints on these plants (a nuclear reactor cannot be switched on and 
off in a minute, some other stuff has to cool down etc.). As often in OR (from what 
I know) this is done by having big LPs and playing with them, adding new 
inequalities, trying to use the structure to speed the computation, having 
branch and cut routines etc. 
A challenge is to break symmetries in these LPs. Suppose you have two identical 
nuclear reactors, then if you use one or the other, you will have the same cost, 
thus you can have many many optimal solutions. This is bad for a branch and cut 
strategy, where the ideal case is to have only one optimal solution, and to be 
cutting all the other branches. Cécile showed ways to solve this problem, and 
there is a whole litterature about this. 
This reminded me of another PhD defense with symmetries: the one of 
[Victor Verdugo](https://sites.google.com/view/vverdugo/). Victor had a part of 
his PhD work on how to break symmetry for 
[sum-of-squares](https://en.wikipedia.org/wiki/Sum-of-squares_optimization), and 
the timing for this blog post is pretty good: the paper just appeared on arxiv, 
[here](https://arxiv.org/abs/1811.08539).

## Double-blind for DISC
The conference [DISC](http://www.disc-conference.org/wp/) will go 
double-blind next year.[^2] At first I was sceptical about this idea, 
because of the usual reasons: extra-work, extra-care when talking to 
people, not very effective, we should not super-optimize conferences because
journals are the most important etc. But recently I had to review a paper by 
people from a university I've never heard of, and I felt that, before even 
starting I had a big bias. I think double-blind is exactly about 
removing this bias. In other words, I heard many times that the 
problem is that well-known people get their papers accepted although 
they are not good enough, and I think this cannot really change (because 
of arxiv, favourite topics, writing style), but it's the other side of the 
spectrum that can be made more fair. So let's see how it goes.

## A few points on networks and games
I attended a talk at LIP6 by 
[Ariel Orda](http://webee.technion.ac.il/Sites/People/ArielOrda/) on game theory 
and networks. The talk described two very interesting works, but 
I just picked a few non-specific things that caught my interest. 

### Network formation games
The first topic is about understanding the structure of real-world networks, by 
finding ways to build algorithmically networks that have similar properties. 
A well-known generation algorithms is the 
[Barabási–Albert model](https://en.wikipedia.org/wiki/Barab%C3%A1si%E2%80%93Albert_model) 
where nodes basically arrive one by one and choose who to be linked to 
based on the degree of the nodes that already arrived. There is a second 
type of network formation model that I didn't know,[^3][^4] which is to start 
with a set of fixed nodes and to make them play a game with the edges. 
For example maximize the payoff in a game where links cost something, 
but having short paths to every node is rewarded. 
These are called network formation games.  

### Monetary transfer
The second idea is monetary transfer. Suppose you have a Nash equilibrium 
that is very bad (for some definition of bad) because each player when 
maximizing its gain is hurting the other players a lot. Then you can introduce
monetary transfer, that consists for two nodes to agree that if the 
first does this thing that decreases its pay-off but increases the pay-off 
of the second player, then the second player will give part of its 
pay-off to reimburse him, and both will be happier. Natural idea to 
consider, but that I had never heard of.

### Using motifs to validate a model
The third thing is a tiny thing: I knew that people studying social 
networks are obssesed with finding motifs (small graphs that appear more 
often than others), but I was not sure why. It could be just to have 
more knowledge about the relationships, but in Ariel Orda's talk, it was 
also a way to validate a model. Basically in real-world graphs this and that 
motifs are very common, we don't know why, and previous generative 
models did not have this property, but their model could capture this. 
To my knowledge, parameters such as the diameter, or the clustering 
coefficient are canonical ways to validate a model.

### About the price of anarchy, selfiness and collaboration
The [price of anarchy](https://en.wikipedia.org/wiki/Price_of_anarchy), 
is the ratio between the social cost when each players tries to optimize 
its own pay-off, and when all the players play the startegy that minimize 
this social cost. It is often said that this price is the price to pay 
when players are selfish. But it is not completely true, it is also the 
price of not collaborating. You can image scenarios in which players have
the option of collaborating but each player will agree only if it ensures 
 a better pay-off. That is the players are still selfish but 
they can talk to each other and make agreements. 
This can change the outcome a lot. Then one 
will consider what is called a Nash bargaining solution.


#### Footnotes 
[^1]: If you are interested, see [Fabian Reiter's very nice PhD thesis](https://arxiv.org/abs/1805.06238).
[^2]: See [this tweet](https://twitter.com/JukkaSuomela/status/1065259077738082304)
[^3]: There seems that there is no third well-known way to generate networks, at least in the [wikipedia article about network formation](https://en.wikipedia.org/wiki/Network_formation).
[^4]: Actually I somehow knew because of [this paper](https://dl.acm.org/citation.cfm?doid=3178876.3186122) by my PhD advisor and collegues, but I had forgotten.

