---
layout: post
title:  "Decentralization, Scalability, and Fault Tolerance of Bitcoin"
author: "Stan Larimer & Daniel Larimer"
categories: article 
---
Bitcoin is all about decentralizing the control over money through objective consensus on ownership.  What often gets lost in the discussion is the
difference between decentralization, scalability, and fault tolerance.   Bitcoin is an example of a decentralized system whose scalability
is limited by the power of an individual node rather than the combined power of all nodes.  This means that a system's ability to become 
distributed for fault tolerance, decentralized for control, and scalable for performance are not linked together by the number of nodes. In
fact we could say that attempts to combine these roles via the same mechanism will carry with it the combined limitations rather than the
combined benefits.   Hence economies of scale and free market competition will tend to minimize unnecessary fault tolerance (redundancy) while centralizing for
performance. If we are not careful this will result in centralization of control.

When the BitShares developers get a little uppity, I love to remind them that what they are doing is not exactly rocket science.   

But, while trying to find a way to communicate the architecture of BitShares to folks on other forums, I've stumbled on the following description, drawing on my past experience with *continuously reconfiguring fault-tolerant flight control systems*.  (Yes I wrote a technical report with that title back before there was an Internet or even a word processor.)  See if you buy this way of describing the BitShares architecture:

We tend to get three different attributes mixed up causing endless confusion even among men of good will.

1. Throughput Scalability 
2. Fault Tolerance 
3. Decentralized Control

These are three different concepts.  

## Fault Tolerance
We are saying 101 highly-reliable, tested and proven, hand-picked parts dispersed across the globe and selected by the entire owner population is sufficient redundancy to achieve reliable fault tolerance.  The only thing those parts can do is -- do their job to spec.  We can observe their performance and swap them out in ten seconds if they don't perform to spec. So, really, they are just interchangeable slave machines.  Producing the blocks is a mindless task. 

Selecting which parts make up the machine is where the power lies.

## Decentralized Control  
The total decentralized population of the all owners participate in selecting the most reliable machines to run the network. Those 101 parts have no power over the owners. 101 dispersed redundant parts is a decentralization red herring! That's not where control lies. Those 101 chosen nodes can be completely reconfigured or replaced by the fully decentralized participating owners in 10 seconds.  

<center>
BitShares has decentralized p2p control<br/>
of a distributed, fault-tolerant computer<br/>
implementing an autonomous unmanned company<br/>
running a decentralized crypto currency exchange <br/>
which produces stable smart-coin products.
</center>

## Throughput Scalability
 Any of the 101 nodes can scale up by adding parallel machines, side chains, and a thousand inventions we haven't dreamed of.   When we get to a billion owners and need a thousand machines per node, we can do that.  It will still be decentralized enough to ensure that the 101 (now bigger) parts that make up the distributed, fault-tolerant machine will perform their mindless slave jobs reliability - from positions scattered across 24 time zones.

Those million decentralized owners do not want to have to think about managing more than 101 redundant parts to their machine. 101 is plenty, maybe too many, for the average owner to keep track of how they are performing.  Adding more parts reduces the degree to which each part can be vetted and therefore reduces the system's reliability.   Total reliability is a combination of node redundancy and node reliability via reputation-based vetting.

In BitShares, absolute control is fully decentralized down to the votes of every single atomic BTS satoshi.  You can't get more decentralized than that. 

## Bytemaster's Conclusions 

At the end of the day it is all about decentralization of influence.  It doesn't matter that everyone is theoretically able to enter the lottery to gain the honor to produce a block if the same people win the lottery the majority of the time.  Economies of scale will always force systems toward centralization via the removal of unnecessary redundancy in order to compete in the free market.   Absent a means of delegating block producing influence to another party, any proof-of-*something* system will tend to deny small players any influence.   

Bitcoin & Nxt both support delegation of influence through mining pools and leased forging.   Bitcoin and all of the alt-coins have proven that left to its own devices the market will realistically support no more than 10 pools.  As the network scales block producers will be competing to lower fees.  This inevitably means placing their full nodes in locations with cheap bandwidth and computers optimized for signature verification and database speeds.  Users of the network will eventually start creating transactions with fees lower than would be profitable for any unspecialized block producer to process.  It just isn't worth the time, money, and effort for companies to run a block producing node at scale.  

Nxt leasing and Bitcoin mining pools will ultimately result in fewer than a dozen organizations producing over 51% of all blocks within the confirmation window.  I did a random sampling of Nxt block producers and in a matter of minutes identified 10 people who have collectively produced 30% of all blocks in Nxt history.   At this rate I could likely find that 51% of blocks being produced by fewer than 40 people.   There may be over 300 people participating, but the vast majority of blocks are produced by a small minority. 

What we learn from this is that we must decentralize control with a different mechanism than we achieve fault tolerance.  It is more important to have decentralized control over who produces blocks than to have no control over who produces blocks.  If token holders don't control who produces blocks, then centralized block producers will control who owns the tokens.   
