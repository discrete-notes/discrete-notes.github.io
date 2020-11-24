---
layout: post
title: SSS 2020 report 1&#58; Pulse distribution and a nice open problem
redirect_from: "/2020/11/24/sss-2020-1-pulse-distribution/"
permalink: sss-2020-1-pulse-distribution

I attended [SSS 2020](http://www.cse.msu.edu/~sandeep/SSS2020/index.html) last 
week, and I'll try to write a few posts about things I 
found interesting. (I'm trying to not delay too much the publication of these 
posts so they won't be very deep nor polished. Comments are most welcome.)

The first post is about a problem of pulse sychronization and about the nice 
open problem about a "simple" discrete random process. 


![](assets/austin.png){: .center-image width="100%"}
<p align="center"><small><i>
Austin's skyline. (The conference was supposed to be in Austin.)
</i></small></p>

[Ben Wiederhake](https://people.mpi-inf.mpg.de/~bwiederh/) gave a nice short talk 
about the paper 
[TRIX: Low-Skew Pulse Propagation for Fault-Tolerant Hardware](https://arxiv.org/pdf/2010.01415.pdf)
(joint work with [Christoph Lenzen](https://people.mpi-inf.mpg.de/~clenzen/)). 
The talk video is [here](https://mediaspace.msu.edu/media/SSS+2020A+Day+1A+Session+1A+Talk+4A+TRIXA+Low-Skew+Pulse+Propagation+for+Fault-Tolerant+Hardware.+Ben+Wiederhake+and+Christoph+Lenzen/1_mb5lmdso/189882373).

The setting is the following. It is common in computers to have several "devices"
that needs some common clock. A classic way to have that is to have one clock 
signal which is broadcast to the devices through a binary tree, like on the 
picture below. 

![](assets/pulse-tree.png){: .center-image width="70%"}

Now, if there is some abnormal delay on a link, or even a link failure, then the 
clocks signals received by the devices can be badly synchronized. The paper 
introduces another type of synchronization network. (The specific reasons for 
which this is realistic and meaninful can be found in the paper, I won't discuss 
them). The authors consider a kind of generalized grid.
Every node at position $(x,y)$ in the grid belongs to layer $x$, and is linked 
to three nodes from the previous layer: $(x-1,y-1)$, $(x-1,y)$ and $(x-1,y+1)$, 
its predecessors.
Then it is also linked to three nodes from the next layer, its successors, which 
are $(x+1,y-1)$, $(x+1,y)$ and $(x+1,y+1)$.

![](assets/pulse-grid.png){: .center-image width="70%"}

The nodes of the first layer are synchronized, and send a pulse at the same time. 
The key point is that every node sends a pulse to its children when it has 
received the pulse *from two of its predecessors*. 
This ensures a kind of fault-tolerance: if a node has crashed, then the 
sychronization can still happen perfectly, as its successors will still receive 
two pulses. 

![](assets/pulse-fault.png){: .center-image width="70%"}

But what the authors focus on is the skew between pulses of different nodes. 
Because the wires are not perfect, it can take some time $\tau_1$ for the signal
to go from one node to one of its successors, and time $\tau_2$ to go to another
successor. Now a question is, with this grid-like structure, how much difference
can there be between pulses at different nodes? 

To get a more precise and clean question, the authors consider that with 
probability 1/2, the signal traverses the link in time 0, and with probability 
1/2 it traverses the link in time 1. And they focus on the following question: 
given two nodes of the same layer, that are adjacent (e.g. some $(x,y)$ and
$(x,y+1)$), what is the difference between the times at which they receive the 
signal? (This difference is called the skew)

The authors show by numerical experiment that the maximum skew at some layer $H$
is lower than $\log \log H$, and other statistics showing that the systems works
very well. 

The obvious question from a TCS point of view is: can we show good bounds on the 
process? This seems very hard. Already in 2018, the authors 
mentionned the problem at the 
[Helsinki February workshop](https://research.cs.aalto.fi/da/feb2018/), and 
could not get a good bounds. One of the reason why this is difficult is that 
at each node some input is lost: if the three pulses arrive at time $t$, $t'$ 
and $t''$, then the nodes "fire" at time $t'$, and does not care about $t''$. 
In some sense $t''$ is lost. 

 


