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

## Distributed computing: a locality-sensitive approach, by Peleg

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

The last three items are sets of lecture notes, taking the form of 
neat online textbooks. They all cover the basics, e.g. Linial's coloring, but 
they also have their own specific things.

## Distributed algorithms, by Suomela

A first online textbook is
[Distributed algorithm](https://users.ics.aalto.fi/suomela/da/da-print.pdf)
by Jukka Suomela. It has a focus on showing the similarities and differences 
between different models, such as port numbers and unique identifiers, and on the 
graph theory tools, such as covering maps and Ramsey theory.

## Distributed graph algorithms, by Ghaffari

A second text book is
[Distributed graph algorithms](https://disco.ethz.ch/courses/podc/lecturenotes/LOCAL.pdf)
by 
[Mohsen Ghaffari](https://people.csail.mit.edu/ghaffari/). 
It is a shorter text, with a focus on algorithmic techniques, e.g. network 
decomposition. 

## Network algorithms, by Kuhn

A set of lectures notes by [Fabian Kuhn](http://ac.informatik.uni-freiburg.de/kuhn/)
is available chapter by chapter on
[the course webpage](http://ac.informatik.uni-freiburg.de/teaching/ss_18/network-algorithms.php).
It has a broader topic with, in addition to coloring, MIS and cie, chapters on 
leader election and dynamic networks for example.

### In French
Also, if you read French, you may be interested in 
[Algorithmique distribuée pour les réseaux](https://www.irif.fr/_media/users/pierref/notes_algo_distribue.pdf)
by [Pierre Fraigniaud](https://www.irif.fr/users/pierref/index), and 
[Algorithmes distribués](http://dept-info.labri.fr/~gavoille/UE-AD/cours.pdf) 
by [Cyril Gavoille](http://dept-info.labri.fr/~gavoille/).
