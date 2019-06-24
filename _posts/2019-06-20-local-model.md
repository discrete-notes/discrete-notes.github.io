---
layout: post
title: Material on distributed graph algorithms
redirect_from: "/2019/06/20/local-model/"
permalink: local-model
---

This post is a list of pointers to books and surveys about distributed graph 
algorithms (LOCAL model, CONGEST model, and friends).
I probably missed some texts, as typing "local model" in a search engine 
is not very helpful if you are not looking for top model agencies. 
Other references are most welcome! 

![](assets/local.png){: .center-image height="500px"}

---

## Distributed computing: a locality-sensitive approach, by Peleg, and other references

[Distributed computing: a locality-sensitive approach](https://epubs.siam.org/doi/book/10.1137/1.9780898719772)
by [David Peleg](http://www.weizmann.ac.il/math/peleg/) is the classic book 
about the local model. It's from 2000, so it's getting a bit outdated in terms 
of results. 

## Distributed graph coloring, by Barenboim and Elkin

[Distributed graph coloring](https://www.cs.bgu.ac.il/~elkinm/book.pdf)
by 
[Leonid Bareboim](https://www.openu.ac.il/personal_sites/leonid-barenboim/)
and [Michael Elkin](https://www.cs.bgu.ac.il/~elkinm/), is a more recent book, 
with a focus on coloring. It explains quite a few techniques, and has a list of 
open problems (some of these problems have been solved already).

## Survey of local algorithms, by Suomela
The [survey of local algorithms](https://users.ics.aalto.fi/suomela/doc/local-survey.pdf)
by [Jukka Suomela](https://users.ics.aalto.fi/suomela/) is the reference for 
results about constant-time computations in the local model.

## Distributed algorithms, by Suomela

A neat online textbook is
[Distributed algorithm](https://users.ics.aalto.fi/suomela/da/da-print.pdf)
by Jukka Suomela.
In addition to the classic topics such as coloring, that are contained in most 
references listed here, it has a focus on showing the similarities and differences 
between different models (such as port numbers and unique identifiers), and on the 
graph theory tools that can be used (such as covering maps and Ramsey theory).

## The Swiss-German lecture notes

There are several courses related to the local model that are taught in 
Switzerland and South Germany. They are rather close one from another, as they 
stem from the same Zurich source (but then they evolved on their own). 

* The current version of the original source is 
[Principles of Distributed Computing](https://disco.ethz.ch/courses/podc/), 
by [Roger Wattenhofer](https://disco.ethz.ch/members/wroger) (and more recently
[Mohsen Ghaffari](https://people.csail.mit.edu/ghaffari/) but his part is 
covered below). In addition to the classic topics of synchronous computing, it 
covers some topics at the boundary with asynchronous computing (such as 
synchronizers), or fully asynchronous (such as shared objects).

* A set of lectures notes by [Fabian Kuhn](http://ac.informatik.uni-freiburg.de/kuhn/)
is available chapter by chapter on
[the course webpage](http://ac.informatik.uni-freiburg.de/teaching/ss_18/network-algorithms.php).
The topics are very close from the ones of the bullet above. Two topics that 
appear only here: dynamic networks and and 
[network coding](https://en.wikipedia.org/wiki/Linear_network_coding). 

* Another set of lecture notes is 
[Theory of Distributed Systems](https://www.mpi-inf.mpg.de/departments/algorithms-complexity/teaching/winter18/tods/), 
by [Christoph Lenzen](http://people.mpi-inf.mpg.de/~clenzen/). It covers 
(in addition to the classic material), chapters on self-stabilization and 
routing. 

* Probably the most recent course is
[Distributed graph algorithms](https://disco.ethz.ch/courses/podc/lecturenotes/LOCAL.pdf)
by 
[Mohsen Ghaffari](https://people.csail.mit.edu/ghaffari/). 
It is a shorter text, with a focus on algorithmic techniques for the local model, 
e.g. network decomposition. 

## Material covering the basics or specialized content

A standard book is 
[Distributed Algorithms](https://www.elsevier.com/books/distributed-algorithms/lynch/978-1-55860-348-6)
by [Nancy Lynch](http://people.csail.mit.edu/lynch/), but most of the book is 
off-topics for this post, because it deals with asynchronous systems.

Yet another reference (with little material on the LOCAL model) is the online 
textbook 
[Notes on Theory of Distributed Systems](http://www.cs.yale.edu/homes/aspnes/classes/465/notes.pdf)
by [James Aspnes](http://www.cs.yale.edu/homes/aspnes/).

If you look for [self-stabilizing algorithms](https://en.wikipedia.org/wiki/Self-stabilization)
then a reference from 2000 is 
[Self-Stabilization ](https://mitpress.mit.edu/books/self-stabilization) 
by
[Shlomi Dolev](https://in.bgu.ac.il/en/natural_science/cs/dolev//Pages/default.aspx), 
and a very recent one is 
[Introduction to Distributed Self-Stabilizing Algorithms](https://www.morganclaypool.com/doi/abs/10.2200/S00908ED1V01Y201903DCT015)
by
[Karine Altisen](http://www-verimag.imag.fr/Karine-Altisen,102.html?lang=en)
[Stéphane Devismes](http://www-verimag.imag.fr/~devismes/WWW/introduction.html)
[Swan Dubois](https://pages.lip6.fr/Swan.Dubois/)
and 
[Franck Petit](https://pages.lip6.fr/Franck.Petit/).

### In French
Also, if you read French, you may be interested in 
[Algorithmique distribuée pour les réseaux](https://www.irif.fr/_media/users/pierref/notes_algo_distribue.pdf)
by [Pierre Fraigniaud](https://www.irif.fr/users/pierref/index), and 
[Algorithmes distribués](http://dept-info.labri.fr/~gavoille/UE-AD/cours.pdf) 
by [Cyril Gavoille](http://dept-info.labri.fr/~gavoille/).

---

Thanks to Jukka Suomela for pointing out some references.
