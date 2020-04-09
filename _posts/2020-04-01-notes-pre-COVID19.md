---
layout: post
title: Notes from pre-COVID19 times
redirect_from: "/2020/04/01/notes-pre-COVID19/"
permalink: notes-pre-COVID19
---

Hi there! After abruptly coming back to France because of the virus, I resume
blogging (instead of traveling, basically). Here is a set of notes that I wrote 
before the quarantine and everything.  

--- 

![](assets/grafitti-donut.jpg){: .center-image width="95%"}

---

## Shapley value

The [Shapley value](https://en.wikipedia.org/wiki/Shapley_value) 
is a concept in game theory. It basically describes how a 
group of players that have played collaboratively, should share the pay-off of 
the game, taking into account that some players have contributed more than others. 
In other words, it is a way to measure how important is each player for the team. 
For some settings it is proved to be the optimal way to share the gain, with 
respect to some objective of fairness.

The setting is the following. There are $N$ players, $1,2, ..., N$, and a 
function $f$ from the subsets of players to the set of possible pay-offs (eg $R$). 
For a subset $S$ of players, $f(S)$ is the pay-off that the players of $S$ would 
get as a whole if they were to collaborate together. 

Now, assume that all players collaborate, and get some pay-off $P$. How should 
we distribute $P$, using $f$? The idea is the following. First chose an 
arbitrary order on the players, for simplcity, let say the natural order $1, 2, 
...,N$. Then player $1$, gets $f(${$1$}$)$, player $2$ gets $f(${$1,2$}$) - 
f(${$1$}$)$ etc. 
That seems pretty reasonable: every player gets the marginal value it adds
to the pay-off. Now this is not always fair, because of the ordering that we 
chose arbitrarily. Therefore one normalizes this by taking the average over all 
permutations of the individual pay-offs. This is the Shapley value.

[Thanks to [Eric Remila](https://perso.univ-st-etienne.fr/remila/) for telling 
me about this.]

## Stochastic dominance

Stochastic dominance is a concept of probability that is useful in (algorithmic) 
game theoretical settings, such as 
[secretary-type problems](https://en.wikipedia.org/wiki/Secretary_problem).

Let $A$ and $B$ be two real random variables. Then $A$ 
[stochastically dominates](https://en.wikipedia.org/wiki/Stochastic_dominance)
$B$ if for every $x$, $P(A\geq x)\geq P(B\geq x)$, and for some x, the 
inequality is strict. In terms of cumulative distribution function, this means 
$F_A(x)\leq F_B(x)$ for all $x$, and with strict inequality for some $x$. 

This notion is useful in the randomized online setting: you want to show that 
your online algorithm obtains, in expectation, at least half the payoff of a 
"prophet" that would play knowing all the game in advance. Then 
it is sometimes useful to show that your algorithm stochastically dominates 
"half the prophet".

[I heard about this by working in the group of José Correa in Santiago de Chile.]

## Polygonization, a problem not known to be easy or hard

There are not so many reasonable problems for which we have neither a 
polynomial-time algorithm nor a proof of NP-hardness. Some well-known are 
[graph isomorphism](https://en.wikipedia.org/wiki/Graph_isomorphism_problem) and 
[integer factorization](https://en.wikipedia.org/wiki/Integer_factorization).
Wikipedia has a list in its 
[NP-intermediate article](https://en.wikipedia.org/wiki/NP-intermediate).
Here is a counting problem that falls into this category. 

A polygonization of a set of points is a simple polygon that visits all the 
points. In the following picture, the points are black and a polygonization is 
drawn in blue. 

![](assets/polygonization.png){: .center-image width="60%"}


The algorithmic problem is: given the point set, count the number of 
polygonizations it has.

See the two posts by Eppstein on special aspects of this problem, 
[here](https://11011110.github.io/blog/2020/01/12/counting-grid-polygonalizations.html) 
and 
[there](https://11011110.github.io/blog/2020/01/29/unflippable-polygon.html).  


## Liquid rope coiling and discrete model 

When you pour some honey on a pancake, you can see that the honey behaves a bit 
like a rope and can get some rotational movement when touching the pancake. 
Something like this: 

![](assets/miel.png){: .center-image width="40%"}

[See also [this video](https://www.youtube.com/watch?v=lZbOV8BIOt8) by Jearl 
Walker.] 

Something strange about this is that there is no reaon a priori for the movement
to be rotational: it's just something (the honey) falling on something else 
(the pancake). I was curious whether this could appear in a very simple discrete 
model. Here is a naive model, which probably makes little sense, but shows
some rotation, without explicitely refering to a rotation.

Start with an hexagonal grid representing the pancake (because it's easier than 
a square grid). The yellow cell is where the honey is currently arriving, and 
the orange circle is the projection of the origin of the honey (e.g. the spoon) 
on the pancake.

![](assets/miel1.png){: .center-image width="40%"}

Now there are two forces. One is the "speed" of the yellow patch, that simulates
the fact that the honey tends to go where there is less honey, and the very last 
cell visited has more, so is repulsive. It is represented by the yellow 
arrow. The other one is the attraction of the orange circle, that simulates the 
fact that the honey is still "tied" to the spoon. It is represented by an 
orange arrow. Now the average of the two forces is the red arrow, that is 
pointing to the next cell.

![](assets/miel2.png){: .center-image width="40%"}

The proccess is repeated, and the yellow patch is circulating around the 
cell with a orange circle. 

![](assets/miel3.png){: .center-image width="40%"}

Well it's not a very fancy model, in particular it doesn't make a difference 
between honey on a pancake, and a planet around the sun, but maybe it can be 
improved..!

Anyway, physicists prefer continuous models, and a paper about the modelization 
of liquid rope coiling is available 
[here](https://www.annualreviews.org/doi/10.1146/annurev-fluid-120710-101244).

[I learned about research on liquid rope coiling in 
[this article](https://www.pourlascience.fr/sd/physique/les-acrobaties-des-filaments-liquides-8027.php)
in the French popularization magazine "Pour la science".]


## Other notes
* A latex commands that some of my coauthors didn't know: 
<code>\scalebox{x}{picture}</code> allows to scale a picture by a factor x.

* After trying various techniques and packages to write comments in latex files, 
I ended up simply using text in color with 
<code>\textcolor{color name}{text}</code>, but sometimes (eg for the revision of
a journal paper), one needs to color a large patch of text, and 
<code>textcolor</code> does not allow this. For example you cannot color two 
sections. Then I rediscovered, that one can simply change the text color at any 
point with <code>\color{color name}</code>.

* Eppstein has a 
[blog post](https://11011110.github.io/blog/2020/02/22/applications-maximum-matching.html) 
about applications of maximum matching algorithms, including kidney exchange, on 
which I have worked recentely. 
(As [already mentionned](./march-2019-notes-1) on this blog, 
[here](https://cstheory.stackexchange.com/questions/19759/core-algorithms-deployed) 
is a stack exchange thread on "core algorithms deployed".) 
