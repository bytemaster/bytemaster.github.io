---
layout: post
title:  "Review of Casper, Ethereum’s proposed Proof of Stake Algorithm"
author: "Daniel Larimer"
---

Vlad Zamfir of Ethereum recently made a [blog post](https://blog.ethereum.org/2015/08/01/introducing-casper-friendly-ghost/) describing a new Proof of Stake algorithm called Casper “the friendly ghost”.   Its name is derived from its relationship to the GHOST (Greedy Heaviest-Observed Sub-Tree) proof-of-work protocol.  For the full details of the proposed approach see their blog post.

## Overview  

My high level understanding of the protocol is that anyone can participate in block production by posting a bond.  After posting a bond you have an opportunity to bet on which block will be included next.   The incentives are such that you make money by betting with the eventual consensus and lose money by betting against the consensus.   Any crypto-graphically provable misbehavior results in the forfeit of the bond.   

An analogy can be made to proof of work where each miner is betting with their hash power on which block will be accepted.  If they bet wrong then any block they produce will be orphaned causing them to lose money.   

This protocol has several nice properties:

 1. Anyone can participate 
 2. Consensus can be reached in a timely manner 
 3. It quickly converges on an irreversible consensus. 
 4. It appears to be free of politics 

Unfortunately, the protocol suffers from the same problems as all other Proof of Stake systems except Delegated Proof of Stake and these problems are fatal.

## Economic Centralization 
 
In a sustainable system, income from transaction fees must be sufficient to cover the cost of participation.   Under Casper, your income is proportional to how much stake you have available to bond and how well you bet.   If we assume everyone bet correctly 100% of the time and there was perfect consensus then transaction fees would be divided proportional to stake.   Under such a system, costs of operating a full node are constant but the potential income is dependent upon stake.   Anyone without sufficient stake would be unable to participate profitably.    Furthermore, those with the most stake will have the highest margins.  The end result of this economic arrangement is that participating in Casper will only be profitable for a small subset of whales, likely a dozen or less.   The only way to increase participation would be to increase fees which will primarily pad the pockets of the whales who have the highest margins while the smallest participating stakeholders barely break even. 

## Incentive to Coordinate 

In order to minimize the cost of bad bets, the participating bettors would collude via a side-protocol.  The likely outcome of the collusion would be a protocol where they agree to take turns producing blocks and then betting on them.   This is very similar to how mining pools allow users to collude by combining hash-power and how mining pools themselves collude to resolve hard forks like March 2013.    The most profitable outcome for all parties of the system is to agree in advance.   A side effect of this collusion is that the large colluding stakeholders can make the only rational bet a bet that follows the colluders.    To make an analogy with proof-of-work, suppose someone had 51% of the hash power and decided to refuse to include blocks produced by anyone else.   The other miners have no choice but to join the attacker or lose money.   In the same way, everyone betting on the next block has no choice but to bet with the “deciders”.   

## Leeching with Sure Bets 

Once it is clear who the “deciders” are it becomes safe for everyone else on the network to simply follow the leader and place bets without actually performing any validation.  These “sure-bets” will end up diluting the revenue earned by the actual block producers/validators.   Taken to the extreme the end result is economically similar to burning all fees and having all validators performing the service for free simply to gain appreciation of their stake.  In effect, if you had 1% of the stake, you would gain 1% of the fees which may not cover the cost of operations or the risk to your stake. 

## High Latency compared to DPOS 

Even with all parties rapidly converging, the final result will have performance characteristics similar to Ripple.   The mere fact that it takes multiple iterations of bets to confirm a transaction means that it will take several times longer than DPOS to converge.  The speed of light limits how fast nodes around the world can communicate and therefore limits how fast each iteration can occur.   It takes at least 1 second per iteration to get feedback from around the world.   We can conclude that it will take casper several seconds to perform enough iterations to confirm a transaction in the absence of collusion.    In the presence of collusion Casper takes on the behavior of DPOS which assumes collusion of elected block producers to enable 1 second average confirmation.  

## Conclusion 

Casper is an innovative approach that will probably work in the same way that Proof of Work, Peercoin, Nxt, and Ripple all ‘work’:  a consensus will be reached, transactions will be confirmed, double spends will be prevented.    Unfortunately, it will also fail in the same ways as every system before it:  unaccountable centralization of control in the hands of a concentrated minority.   The system will ultimately depend upon large stakeholders who depend upon external revenue sources to cover the cost of operating a full node at scale.   Only Delegated Proof of Stake ensures that all stakeholders have their opinion included in an economically viable manner.  

