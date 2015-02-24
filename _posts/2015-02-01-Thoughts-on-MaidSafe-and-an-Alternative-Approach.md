---
layout: post
title:  "Thoughts on MaidSafe and an Alternative Approach" 
author: "Daniel Larimer"
categories: article 
published: false
---
I would like to provide some additional thoughts on MaidSafe based upon [feedback and corrections](https://www.maidsafe.org/t/bytemater-bitshares-daniel-larimer-opinion-on-maidsafe/2902/6) that I have received.   In particular I would like to address “farming”, “speed” and “leeching”.  Like I said in my [prior post]({ post_url 2015-01-30-Can-MaidSafe-Decentralize-the-Internet %}), economic incentives will either make or break a project and some of the clarifications have me concerned.  Lastly, I would like to present an alternative approach to providing censorship resistant distributed storage.  

Once again I would like to state that most of my opinions are based upon speculative assumptions derived from what I have read.  My arguments do not depend upon the facts being 100% correct because any slight variation on the facts is unlikely to change the outcome.  I will post corrections for anything that may be wrong.   

# Leeching 

One of the first things that I was told is that you “pay to put” not “pay to fetch”.   The benefit of “pay to put” is that there are far fewer people storing data than fetching data which means far fewer micro-payments.   This structure greatly concerns me about the profitability and sustainability of the network.   

If I upload a picture of my cat then chances are there will be relatively few fetches.  If I upload a copy of the latest movie then there will be millions of fetches.   Because the data is all encrypted the network has no way of knowing how often the content will be fetched and thus no way of knowing how much to charge in advance.   

The only viable option is for the network to delete the content unless the person who stores it continues to pay enough to cover all of the fetching.  This would cause the network to operate very much like traditional hosting and would make it much more costly to store and maintain a movie with millions of downloads than to store a picture of my cat with no downloads.   

As far as I know this is not what MaidSafe has implemented.   For starters I know they have implemented caching of frequently accessed content.  This means that they expect nodes to provide resources to both fetch and serve cached content without being paid.   This is very altruistic but not economically viable.    The only way to “pay nodes” for caching is if they earn SafeCoin as a result of farming which implies that “fees are paid globally” and “prices are fixed centrally”.     

# Pricing 
When you store data on the network you upload it to a “manager node” which is then responsible for deciding where to store it and replicating the data.  The person who uploads the data doesn’t even know where it gets ultimately stored.    

So the question becomes who gets paid when you store an item on the network.  There are several options here and I don’t know which one they are implementing.   One option is to pay the node(s), the other is to “pay the network” by burning Safecoin.   In either case the cost of storing the data is very different than the cost of hosting the data.  

Perhaps the most “telling” question would be “Who gets to set the price of putting data?”   If the price is global (constant) and the goal is decentralization then the price will have to be relatively high so that as many people as possible can contribute to it profitably.  If you set the price too low then only those with cheap/bulk bandwidth and storage will be able to contribute to it profitably and therefore the network will centralize.    If you make the price variable based upon provider then you get into a complicated cost/benefit analysis for every put operation. 

# Farming 

MaidSafe has a novel approach to ensuring data integrity with a “Proof of Storage” system.  Farmers will pick random chunks of data and request nodes to prove they have stored it.   The more you store and the more you farm the more safe coin you will earn.   

This is a very expensive kind of proof-of-work that consumes network bandwidth and CPU resources even while the network is “idle”.  This represents a fixed cost to the network that is paid for by creating new SafeCoin.   In the long-run this will have to be paid for out of fees if it is necessary to ensure data integrity.  

The result of Farming will be the cancerous growth of added storage that will be paid for by debasing SafeCoin holders.   It would be like a startup paying to add an excessive amount of server capacity before demand even exists.   They have some throttling based upon demand, but like all Proof of Work systems there is a heavy carrying cost.  

# Speed 

In my prior post I claimed that MaidSafe wouldn’t be as fast as centralized alternatives.  People quickly pointed out it would be like Bittorrent where you can download from 3 people at once to maximize your speed.   

The assumption here is that the individual user has more bandwidth than a centralized server can provide.   Have you ever downloaded from iTunes?  It is ALWAYS faster than downloading the same content from a popular BitTorrent with 1000’s of users.  There is no escaping the network overhead of negotiating hundreds of connections and maintaining a “tit-for-tat” incentive structure. 

That said, bandwidth isn’t what matters.  Latency is far more important for user experience, especially web browsing.   In a large network with peers spread all over the world, you can expect that the average request will go 25% of the way around the world and give you a latency of 250ms per request.    

When you have a large network with 1 million nodes, a single lookup could require log(N) requests and take 5 seconds on average.   You can hide latency when you are downloading large files by pipelining, but you cannot hide latency when web browsing because you don’t know what link the user will click on.   

You can get around latency by having a centralized server maintain an index of all data and what nodes it is stored on, but the MaidSafe network keeps the storage location secret with large degrees of compartmentalization.   There are few ways to reduce latency in this setup.

# Alternative Approach 

Lets change the paradigm a little bit.  Instead of attempting to create a giant organization that uses layers of middle management to provide a hosting service, lets create a shopping mall with thousands of individual businessmen competing to provide service.   

Businesses agree to standards and often locate near one another in shopping districts because they gain network effects.  If someone is already in the mall to buy from other vendors then it will be easier to compete if you open up a storefront in the same mall and accept the same forms of payment.

All that is required is a standardized API and a quickly accessed index.  In my view the API would be very simple:  store and fetch.  The content would be required to pass a test for randomization and would be of fixed size (1MB) and addressed by hash.  

Every businessman would be operating a for-profit business where his goal is to maximize profit given his available bandwidth and storage capacity.   To do this he would speculatively store data he expects shoppers walking by his store would want.    If he has low bandwidth and large storage capacity then he will store a large amount high-priced, infrequently sought after data.  If he has high bandwidth and low storage capacity then he will store a small amount of low-priced, frequently sought after data.     The data that is most profitable for the business man to store will depend upon where is shop is located.    Every store can automatically manage their inventory and pricing so that they gain the most profit by reselling all of their available bandwidth and storage at the highest price the market will bare.

# Censorship & Copyright Infringement Liability 

Copyright enforcement is the most common form of censorship.  Any censorship resistant platform will by definition enable copyright infringement.  From this perspective we can simply assume the system is being designed to enable copyright infringement and that this will be the primary, most profitable, use case. 

Individual business men would have to structure themselves as “caching proxies” so that they can claim immunity from DMCA copy-right infringement claims.  In the event that the caching is insufficient all that is necessary is to provide an automated way for lawyers to file take-down requests of individual chunks of data.

Here is the key to dealing with the DMCA:  the law requires a relatively expensive process of writing a letter that identifies the copyrighted work, where it is being stored, and proving they are the copyright holder.    There are services such as [dmca.com](http://dmca.com) that will automate much of the process, but it still costs TIME and MONEY to submit a take down request.    So long as business men provide an alternative means to take down content that is *cheaper* than filing a DMCA request yet still caries with it full liability for taking down legitimate content then the business operator will avoid any and all liability for copy righted material that is temporarily hosted in part on their server.    

Taking down the content within 24 hours of receiving the notice is sufficient for complying with the law.  This means that those wishing to publish copyrighted works merely have to re-encrypt the work every 24 hours to keep it live *AND* the download service is making a killing charging copyright holders to delete content.    

# Conclusion 

Understanding economics is the key to building these distributed storage systems that are censorship resistant.   You merely have to make the cost of deleting content slightly below the cost of getting a legal request to censor the content.  The free market will take care of the rest.

If there are 1000’s of infringing services all ready and willing to delete content on request then they are all complying with the law, yet the cost of getting the content deleted from all 1000 infringing services is too high to bother. 

By operating legitimate businesses you can have large heavily specialized services that can provide you 99% of the content you need at very low prices.   This means that you avoid the need for micro payments to 1000 different business.  At the same time every individual can use bittorrent tit-for-tat to trade for content that may not be available on the paid-for service.  

MaidSafe will be an interesting experiment and will raise the bar in the field, but I think it has the economic incentives wrong.  Like Bitcoin with proof of work, it will probably take years for the market to fully realize the ramifications of MaidSafe's incentives.  


