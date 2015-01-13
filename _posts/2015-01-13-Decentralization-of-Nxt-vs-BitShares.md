---
layout: post
title:  "Decentralization of Nxt vs. BitShares"
author: "Daniel Larimer"
categories: article 
---

There has been an ongoing debate over the relative decentralization of various projects.  I have made several posts where I analyse things from
both an economic and mathematical perspective and draw various conclusions about the theoretical decentralization of the various protocols.  Today
I discovered that Nxt has already published all of the information necessary to prove my predictions correct.

In my post about [How to Measure the Decentralization of Bitcoin]({% post_url 2015-01-09-How-to-Measure-the-Decentralization-of-Bitcoin %}) I introduced the concept that the distribution of block production matters
far more than the total number of people who can produce blocks.   Specifically, it doesn't matter if 1000 people can produce blocks in a given year,
if 99 out of every 100 are produced by the same individual.   

Today the numbers are in for Nxt with data from [their very own block explorer](https://nxtblocks.info/#section/blockexplorer_charts).  These numbers show that 60% of all blocks are produced by just 15 accounts.  The
Nxt users recommend 720 confirmations for "big transactions" which means that at best 300 people contribute to producing a block in that window.  This makes the
provably false assumption that the last 40% of all blocks are maximumly distributed to 1 person per block.   I can go further and say that in my own samples of the
top producers I found enough block producers that were above 1% and less than 2% that I can safely conclude that after 720 blocks less than 101 unique block 
signers have confirmed the block.

<center>
<img src="/media/nxt_forging.png"/>
</center>

What is even more interesting is the overall speed of the network.  The Nxt blockchain aims for 1 minute blocks, but on average gets only one block every
two minutes.   You can see this on their blocks-per-day chart.  

For small transactions, it is recommended that you wait for 10 blocks or an average of 20 minutes.  During that 20 minute window your transaction will be "confirmed" by 10 people, more often than not those 10 people will be a subset of the 16 most common block producers.  Waiting 40 minutes will not buy you much additional decentralization. 

Compare this to BitShares, which during any 20 minute window has all 101 delegates sign off on your transaction 1.25 times on average making it fully irreversible.  Our delegates are
far more reliable with near 100% participation compared to Nxt forgers at about 50% participation.   

## Decentralization per Minute

This is where I would like to introduce a new concept: speed of decentralization.  The more people you attempt to involve in a consensus process, the longer it takes.  For
Nxt to have a block confirmed by 101 unique individuals would require 7 hours best case.  You can calculate this by assuming that only 4 out of 10 blocks are 'unique' and the
other 6 are from the top 16 producers.   This means 20 minutes for every 4 new unique individuals, or 7 hours.   (20*(101-16)/4)/60 = 7.

## Fault Tolerance 

If BitShares were to lose 50% of its delegates all at once due to a government crackdown the remaining 50 delegates would still be producing a more secure, decentralized, and
distributed ledger with greater decentralization per minute than every other blockchain on the market.   

At the end of the day, speed of decentralization matters to the end user and is actually critically important to overall security.  It is much easier to pull off an attack if
the attacker has 7 hours than if the attacker has mere minutes.   Users want speed and with the latest data from Nxt we can conclusively say that on a logarithmic scale,
BitShares with 101 delegates is over twice as decentralized as Nxt with only 10 signers within the transaction confirmation window.







