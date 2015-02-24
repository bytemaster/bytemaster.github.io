---
layout: post
title:  "Can MaidSafe Decentralize the Internet?" 
author: "Daniel Larimer"
categories: article 
---

I have been following [MaidSafe](http://maidsafe.net/) since before I learned about Bitcoin and I learned about Bitcoin back when I could still mine full blocks with my own CPUs.    Back in those early days MaidSafe was not creating a crypto-currency and instead focusing mostly on distributed storage.  Much has changed since then and there are many great things that MaidSafe is doing.   Today I would like to offer my opinions on their efforts.

My first encounter with MaidSafe was when I was attempting to build my own decentralized storage network.  I was very interested in distributed hash tables and was looking for implementations of the [Kademlia](http://en.wikipedia.org/wiki/Kademlia) algorithm.  I was very excited to find their website; unfortunately, the code was not fully open source at the time and I was forced to wait until they published their latest version.   

When I finally got my hands on their early code I was quite impressed.  These guys are clearly looking to integrate the best software for solving the problem.  What I really liked was their use of [UDT](http://udt.sourceforge.net/) (UDP-based Data Transfer) library which has set a very high standard of performance.    I have also [added basic support for UDT](https://github.com/BitShares/fc) in my own C++ core framework, [fc](https://github.com/BitShares/fc).  

These guys are perfectionists when it comes to coding and software design.  They are frequently discussing ways to optimize code quality in a way that is very refreshing and that I fully appreciate being a bit of a c++ design perfectionist myself.   I have learned over the years that design perfectionism is very costly and results in projects that never get released.   I suspect this is a large part of why MaidSafe is still in testing after over 5 years of development.  

In their pursuit of perfection it appears they have abandoned using the 3rd party UDT library and instead implemented their own [RUDP](https://github.com/maidsafe/MaidSafe-RUDP/wiki/Documentation)  (Reliable UDP) protocol instead.   Having implemented many UDP protocols I can say from experience that they are a lot of work to get right.  I cannot say that I blame them for abandoning UDT because in my experience the UDT implementation has not kept up with the latest asynchronous network structures demanded by high performance networks.   

I realize that I am picking apart a relatively low-level aspect of MaidSafe, but it merely serves as an example of the huge amount of effort that has gone into building their system.  If they ever get this thing released in the wild it will be amazing.   Of course I have been saying that for years.  

Enough with nitpicking their code quality, lets talk about their design.   

## Micro Managed and Overly Complex

The MaidSafe network architecture has become very complex with many specialized nodes each of which is managed and promoted within the system.  Nodes are grouped into blocks of 32 and management nodes direct where files should be stored and are responsible for republishing data.  In their currency system consensus is reached among a group 32 peers.  Existing nodes assign IDs to new nodes and place them in groups.   Every place I turn in their documentation I see a complex set of business rules, routing rules, reputation rules, and other forms of centralized planning.  

Centralized planning is one of those things that is a double edged sword.  On the one hand it can produce extremely optimized results, on the other hand it can be very fragile.  I would compare it to the different ways of attempting to create artificial intelligence:  you can program specific instructions for as many cases as possible, or you can have simple rules that result in an emergent behavior.   The emergent behavior may not be as “clean” or “predictable” but it is far more flexible and robust.    

I am going to say straight up that I have not spent the time to study every design decision made by the MaidSafe team, but my gut tells me that the system is patch work of design hacks attempting to fix issues caused by low level misguided design requirements.   An elegant system would have as few moving parts as possible and be as simple as possible.   Unfortunately, building a network like MaidSafe is attempting to do is not easy.  

Obviously my own project, BitShares, is not immune and I would dare say suffers from some of the same issues.   As you build a project you learn more and that demands change.  Unfortunately change is expensive and  can delay projects that are good enough in the name of perfection.    

Based upon the level of programming talent that MaidSafe has I expect they will deliver a working product that will be among the best distributed storage solutions out there. 

# Economic Challenges 

The biggest issue that MaidSafe faces is designing their economic incentives properly.  Most P2P networks suffer from a problem known as leaching.  A leacher is someone who consumes resources (bandwidth) without contributing bandwidth or paying for it.  This is what makes systems like Freenet, Tor, and I2P so slow.  

If a P2P network can get the economic incentives right then free market competition will take over and provide the highest quality, lowest cost service possible.   If you get the economic incentives wrong then the same free market competition will drive the service into the ground.

The go-to answer is always the same: implement automated micro-payments.    Unfortunately micro-payments are not economically viable, especially in a distributed P2P system.  

Lets assume you download a movie that is 1 GB in size and has been divided up into 1000 chunks each 1 MB.   Because this is a P2P network with a million nodes, you get each chunk from a different peer.  Now it comes time to pay the bill and you discover that you owe 1000 small payments. 

How small should these payments be?   

We know from Netflix that the [cost of providing 1GB of data is $0.01 and falling](http://stopthecap.com/2012/03/08/netflix-cost-of-providing-1gb-of-data-is-less-than-one-cent-and-falling/).  This means that you owe 1000 people each $0.00001 for the MB of data that you downloaded from them.   This is well below the level of what Bitcoin considers dust and would be uneconomical to process even in a very centralized way.  

P2P crypto-currencies are expensive on a per-transaction basis because every transaction gets stored and broadcast by thousands of nodes.   A 256 byte transaction can easily consume over 1 MB of bandwidth at a network-wide level.    From a pure bandwidth-to-bandwidth perspective micro payments are not viable.     To get around this MaidSafe has created a new crypto currency called Safecoin that aims to solve the problem of having to broadcast the transaction to everyone while enabling micro-payments to occur on a “frame by frame basis” as they state in their [white paper on SafeCoin](http://maidsafe.net/docs/Safecoin.pdf). 

> Unlike bitcoin, the SAFE Network does not use a blockchain to manage ownership of coins. Conversely, the SAFE Network’s Transaction Managers are unchained, meaning that only the past and current coin owner is known. It is helpful to think of safecoin as digital cash in this respect, providing safecoin users with more anonymity than they experience with bitcoin.

What I am about to describe is very high level and could be slightly wrong, but I do not think it is necessary to have things “perfect” for my point to be valid.   

If you assume you have a trustworthy, incorruptible, database then all that is necessary is for the maintainer of that database to update the owner of a balance.  This operation is as simple as a signature verification.   In the case of MaidSafe, they have a distributed database as their foundational building block.  All they have to do is ensure that the data is never lost and never corrupted.    To do this they have peers work in groups of 32 to approve all changes to the database.   You can view this kind of like having 1000’s of small Ripple networks with 32 “randomly” selected nodes each.   The network adds and removes nodes from the consensus set as they join/leave the network in a way that doesn’t allow new nodes to control where they end up.   

At the end of the day integrity of your SafeCoin ledger depends upon these 32 dynamically selected nodes not colluding to move your balance or forge new balances.    

If we make the simple assumption that all 32 nodes must receive, process, and reply to every transaction and confirm it with each of their peers and we assume 1 KB per network message then we can derive an estimated bandwidth cost to reach a consensus among 32 peers to be 1024x32x32 or 1 MB.    Mind you this is simply a SWAG (Scientific Wild Ass Guess) and actual bandwidth may be lower.    Even if I am off by a factor of 4, the cost of the micro-payment will be 25% of the value of the entire transaction in bandwidth alone. 

We can also estimate that the time to process a transaction based upon the network latency of two peers on opposite sides of the world.  A simple “ping” message can take 500 ms and every single transaction would likely require multiple round-trips.  This means that it could easily take over 1 second to confirm a transaction if you already had all of your network connections established.  

If you must lookup the peers responsible for managing the coin used in the transaction then that could take log(n) lookups and easily take several seconds on an encrypted network with a million nodes evenly spread all over the world.   These lookup requests will also consume bandwidth.   This isn’t that much better than BitShares which has an average transaction confirmation time of 5 seconds. 

If we view time as a resource, it will likely take longer to process and confirm the payment than to download the content, especially if you have a network connection that can provide multiple megabytes per second and only source 1 MB of data.     

All told I suspect that even with all of the great improvements MaidSafe has made with their coin, it is still not efficient enough to do micro-payments to thousands of nodes outside the friendly environment of their test networks.  I would really like to see an estimate on the “cost per transfer” in terms of time, bandwidth, and CPU on the MaidSafe network by the developers themselves. 

# Competition 

MaidSafe is providing a service: distributed hosting of content.  Their service is designed to be censorship resistant and private.   These requirements significantly increase the cost of their service compared to competitors that are hosting legal content.    A legal competitor can offer simpler pricing, bulk data transfers, faster lookups, and local caches.   When it comes to web browsing, the fast lookups is probably the most important factor.  

There is also the issue that MaidSafe turns the economic model of the internet upside down.  Today everyone expects websites to pay for their own hosting, under MaidSafe every time you click a link you are paying for the hosting costs.    

I predict that contrary to expectations, the MaidSafe network will either be more expensive than alternatives or slower than alternatives.   I highly doubt they can be both cheaper and faster given the overhead of being censorship resistant and decentralized.   I hope they prove me wrong because I want their product to succeed.  

# Conclusion 

I believe MaidSafe will be more successful than those who have gone before it, but will ultimately fall short of the hype surrounding the project.  In a [future article I will outline alternatives that will achieve most of what MaidSafe is attempting in a far simpler and more economical manner]({ 2015-02-01-Thoughts-on-MaidSafe-and-an-Alternative-Approach }).   If I have gotten anything wrong in this article I hope those more familiar with the inner workings of MaidSafe will visit [bitsharestalk.org](https://bitsharestalk.org) and help clarify things.   I truly hope we can work together to build a viable system.  

