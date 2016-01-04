---
layout: post
title:  "The Benefits of Proof of Work"
author: "Daniel Larimer"
categories: article
---

I have long been of the opinion that proof-of-stake is superior to proof-of-work. Today I would like to challenge my own beliefs against the lessons I have learned from over a year of experience with proof-of-stake. In the past I have argued that proof-of-work is wasteful and that the same end result can be achieved much cheaper with proof-of-stake. Today I would like to consider if there is some value to proof-of-work.

<!-- more -->

## Mandatory Disclaimer 

What follows is an idea and perspective on proof-of-work and does not constitute a proposal to modify BitShares, its dilution rate, or its voting algorithms.  

## Work Defined

If we are going to talk about the benefits of proof-of-work, then it helps to have a useful definition of work. In terms of physics, work is defined as *power*  X  *time*.  

        W = Pt

In more general terms, I would define work as something you must *pay* people to do. If it doesn’t cost anything then no work was done. Bitcoin satisfies both definitions of proof-of-work. No one would spend money building specialized hardware and consuming electricity if they weren’t paid to do so. Therefore, Bitcoin’s block difficulty represents mathematical proof that about 25 BTC worth of work was performed. The corollary here is that if you pay a fixed amount of money into a competitive market then market competition will drive the work required to earn that money toward the value of the money. 

We can view Bitcoin Work as Difficulty or HashPower * 10 minutes.

        W = D = HP * 10m 

In proof-of-stake systems we only have power, aka stake. 
I would like you to consider that committing to hold a token for a period of time in the future is work. No one gives up liquidity or locks funds up without expecting interest. The value of the interest paid is therefore proportional to the *work* required to earn it. In the same way, the value of the Bitcoin mining rewards is proportional to the *work* required to earn it.   

Based upon this understanding of work and the value of liquidity we can construct a proof-of-work system that doesn’t require a large amount of money to be transferred to the electric company and mining hardware manufactures. This proof-of-work system does require the money to be transferred to someone though.  In this case, it is transferred to those who committed to hold the token by diluting those who demanded liquidity. This has the effect boosting the value of a token in the short term by postponing sell pressure.



There are two ways to do proof-of-work with stake: 

1. Based on how long you held a coin in the past
2. Based on how long you promise to hold a coin into the future

I will submit for your consideration that what someone did or didn’t do in the past is a risk-free sunk cost similar to renting mining equipment on a day to day basis. On the other hand, promising to hold a coin into the future is a high-risk cost similar to buying mining equipment that takes a year to earn back the initial capital. In terms of security, the future value of a coin is the only thing that matters and this is why option #2 is superior. 

## Everyone Hates Politics 

As blockchains become more complex, politics becomes a bigger and bigger issue. Proof-of-work has this wonderful property of appearing to be free of politics. At a consensus level it is mathematically simple, clean, and fully decentralized. In theory anyone can join the network and start producing blocks.

In practice, proof-of-work has created a pay-to-play model where those who are willing to spend the most to control the network win.  The security in such a system comes from the expense and opportunity cost of mining a particular block and the fact that those doing the mining have a long-term capital commitment and therefore act in a manner to maximize their return.

## Politics is Unavoidable

We have learned from the Bitcoin XT debate that politics is unavoidable. Proof-of-work doesn’t eliminate the politics it simply changes where the politics play out. Rather than a stake-weighted-vote on the blockchain it becomes a web poll or a vote at the Bitcoin Foundation. Mining pool operators end up voting on which fork to support and users vote with their CPU power.

Because politics is unavoidable, it makes the most sense to have the voting done directly on the blockchain.  Bitcoin and Peercoin do this voting by signaling with each block that is produced, but this isn’t the only or most convenient way to do voting. Instead of voting by block production, voting can be done via transactions that indicate how “coindays” or “committed stake” should vote. This voting can even include voting on the set of active block producers and when they should be producing blocks like is done with *delegated-proof-of-stake*. 

The primary challenge with Bitcoin and Peercoin style proof-of-work systems is that only technically savvy individuals who can endure the costs of running a full node on the network may participate in the voting process. The Bitcoin economy solves this problem via cloud mining operations where non-technical users “vote-by-proxy” through hiring someone else to mine on their behalf.


## Voter Apathy 

Under delegated proof-of-stake one of our major challenges is voter apathy. Many people vote once and then forget to change their vote or they vote for a proxy and then forget to follow up. The usual end result is that it becomes difficult to vote out incumbents or vote in new individuals. The presence of voter apathy is a sign that incentives are not properly aligned in the system.
 
This is where migrating from delegated-proof-of-stake to a delegated-proof-of-work system has some serious benefits. When power is in the hands of users who have a long-term capital commitment to a project they have greater incentive to vote because they cannot sell for months or years.  Under the existing delegated-proof-of-stake system most users opt to passively accept the decisions made by others and then vote with their feet by selling the token if they don’t like the result.

When users have the ability to “vote without commitment” the whole community plays a heads-I-win, tails-you-lose game where winning the vote means losing the minority who disengage in the process which then undermines the value of the token.  

## Eliminating Exchange Risk 

Stake-commitment based proof-of-work has the added benefit of reducing the risk posed by centralized exchanges having a large percentage of network stake. In BitShares 25% of the stake is held in the top several exchanges. These exchanges have opted to “not-vote” and thus do not help secure the network, but the risk remains that at any moment they could start voting and have complete control over the network. 

By adding stake-commitment based proof-of-work to the mix, the exchange would be unable to both vote *and* guarantee withdraw on demand. In the best case, the exchange could keep their funds divided into a ladder of commitments such that they could maintain withdraw requests.  

## Is Proof-of-Work Wasteful

The $1 million dollar a day question is whether or not money spent on proof-of-work is wasteful.  To answer this question requires making a comparison among several alternatives. For the sake of this analysis I am going to assume that there is a fixed cost for the proof-of-work and then look at the value of what is solved. Bitcoin and other similar coins use proof-of-work to solve several different problems at the same time:

1. Deciding when the next block should be produced 
2. Deciding who should produce the next block
3. Making it expensive to produce an alternative chain
4. Deciding on the best blockchain
5. Distribution
6. Side Benefits (such as Primecoin)


Of these six things, mining is a terribly inefficient/slow way to determine when blocks should be produced and who should produce them. A lot of work is wasted due to a failure to reach consensus on when and who in advance. This leaves only solving the last 4 problems as a means to justify the cost.

The capital commitment that bitcoin mining enforces creates a kind of self-reinforcing lock-in. People commit to the project, invest in equipment and then are forced to market and promote Bitcoin over a long-term basis in order to recover their costs and make a small profit. Distributing the new coins via mining provides an easy way to get new users on board without having to buy in.  Both of these things have non-zero value.

If BitShares diluted to pay people who produce difficult hashes built off of recent blocks then this work would end up securing the network with the same kind of cost and objective proof as Bitcoin. This would give BitShares the benefits of solving problems #3, #4, #5, and #6 while still retaining the benefits BitShares enjoys in terms of consistent 3-second blocks and the elimination of the need for mining pools.

So the question of whether or not a particular kind of proof-of-work is wasteful depends only on the relative value of *side benefits* to the value spent. In the case of Bitcoin or Peercoin, the *side benefits* include the generation of specialized hardware.  In the case of stake-commitment proof-of-work the *side benefit* is that a large percentage of a token are kept out of circulation which helps increase the value of the liquid tokens.  In other words, instead of investing money outside the ecosystem in hardware and electricity, money gets invested into the ecosystem in terms of long-term investment support. 

When stake-commitment proof-of-work is used, value is transferred from those who need liquidity but choose to hold anyway to those who give it up for fixed periods of time. This creates an investment vehicle that is more than just speculation.  

## Investor vs. Speculator 
Sometimes it is helpful to consider the difference between a speculator and an investor. An investor puts money into a company in exchange for equity that may not be liquid for years. The money the put in goes directly toward funding the company and contributes to the long term value of the company.   A speculator on the other hand could deal entirely in derivatives because they only care about changes in the price. In other words, speculators buy and sell frequently and have no loyalty.  The most that can be said for speculators is that they provide liquidity that allows people to enter and leave the market at smaller spreads.  

A startup company that has 100% of its outstanding stock on the open market has a harder time attracting new investment because newly created shares are competing with existing shares for today’s liquidity.  For this reason almost all startups prefer to tie up investor funds and deny liquidity until they reach IPO or similar liquidity event. 

By diluting speculators to compensate investors with a long-term outlook you can have the best of both worlds.   If all investors lock up their funds for an equal period of time then there is in effect no dilution faced by investors.  On the other hand, if some investors demand liquidity then the other investors profit.

## Distribution
When a new company is created shares are allocated to those who contributed to the company proportional to their contribution.  If two parters each put in equal work in the first year they should each own 50% of the company. If in the second year one of the partners quits, then at the end of the second year one partner should have 67% and the other 33% based upon the amount of work they contributed. 

Based upon this theory, then all dilution to pay for work the company wants done is legitimate. The only question that matters is whether the work being done is *worth* having done.  To use the partner example, if in the second year the remaining partner dug holes and filled them back in then the original partner may be upset because that work did not bring any additional value to the shares.

From this perspective, paying individuals to commit funds for longer periods of time and/or using the rate of pay as a means of regulating price volatility provides enduring value where as paying for miners might have less and less value as the amount of work increases. 

## Conclusion

After a year gaining experience with delegated-proof-of-stake (DPOS) I have concluded that certain kinds of proof-of-work are actually incredibly valuable and useful to an ecosystem's development and that using dilution as high as 15% on short-term speculators to compensate long-term investors can be very helpful in both securing the network, building loyalty, and creating a profitable system.  
