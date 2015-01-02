---
layout: post
lang: en
title:  "Cooperation among Crypto Projects"
author: "Adam Ernest & Daniel Larimer"
categories: 
    - article
---

Vitalik Butern produced yet another great blog post titled [“On Silos”](https://blog.ethereum.org/2014/12/31/silos/) where he called for projects to work together on common infrastructure while focusing on their unique components rather than reinvent the wheel a dozen times.   The primary concern is that there is a lot of duplicated effort among all of the various projects and we should focus on reusing components where possible.

Vitalik and others have expressed concern about fragmentation harming the crypto currency ecosystem.  There are literally dozens of unique projects each attempting to do about the same thing in slightly different ways.   Imagine if all of that duplicate effort could be eliminated and put behind a single effort?  

Many people have adopted a winner-take-all mentality and as a result there are segments of every community that have become very tribal in nature.   No community appears to have a larger tribal component than the Bitcoin community.  Many of these “Bitcoin maximalists” have become extremely hostile toward any project that could potentially compete for market share.   

I agree with Vitalik that cooperation is useful and that the winner-take-all mindset is harmful to the community that adopts it.   We are all interested in crypto-tech for various reasons, but usually it is because it has the power to create a more honest and transparent financial system.  It doesn’t matter who wins so long as the technology is open and transparent.  

Let me quote Vitalik’s hypothetical future: 

> Now, let us paint a picture of an alternative world. Instead of having a collection of cleanly disjoint vertically integrated ecosystems, with each one building its own components for everything, imagine a world where Mist could be used to access Ethereum, Bitshares, Maidsafe or any other major decentralized infrastructure network, with new decentralized networks being installable much like the plugins for Flash and Java inside of Chrome and Firefox. Imagine that the reputation data in the web of trust for Ethereum could be reused in other projects as well. Imagine StorJ running inside of Maelstrom as a dapp, using Maidsafe for a file storage backend, and using the Ethereum blockchain to maintain the contracts that incentivize continued storage and downloading. Imagine identities being automatically transferrable across any crypto-networks, as long as they use the same underlying cryptographic algorithms (eg. ECDSA + SHA3).

That would be an amazing future if all of the projects could be so interoperable.  

The desire to reuse software is always at odds with the “Not Invented Here” mindset that many developers and communities have.   Why should Apple, Microsoft, and Google each develop their own web browser?  Wouldn’t it be better if Apple redirected the resources spent on Safari toward building a better Maps application?   Think of the millions of dollars each and every year that these companies are wasting on duplicated effort.    

From the perspective of those outside the development community it seems obvious that we should reuse work.   Calling for more reuse seems like a very logical approach that will benefit everyone.  It is hard to argue with, in theory.  In practice however, there are reasons the market is currently structured how it is and calls to abandon “silos” are premature. 
As the project lead of one of the largest “silo” projects, BitShares, we are attempting to solve everything from pegged crypto currencies to identity to login and reputation.   Our plans encompass combined efforts of a dozen smaller projects.    We have significant overlap with Ethereum in the long term as we eventually add generic scripting to our blockchain.  

The question is “can we create a single wallet” that will work with all blockchains?   Can we create a single block explorer?   What about a common Login protocol or identity system.  In short we cannot do that today because no systems are mature enough to use out of the box.  Usually these systems are advancing at such a high speed that no two systems could possibly stay in sync for very long.   Developer resources would be wasted maintaining compatibility with constantly changing standards.     

Reuse and standardization have costs that cannot be ignored.  It requires that the reused components be mature, well designed, well documented, and in most cases widely in use already.   It requires communication and consensus among competing interests.  

In short, standardization and reuse is something that can only exist in mature markets after many different “silo” projects have experimented and failed.  Often standards emerge only after one of the silo’s “wins” in some use case.   

## Ease of Use Matters 

I am a long time Mac user and reformed zealot.   I have been programming on the Mac since the 5th grade when my father was teaching me on the Macintosh II.  While I was in college I experimented with adopting Windows and Linux as my primary operating system and gave each a fair shot.   I went back to the Mac in 2004 and haven’t looked back.   

<a href="http://www.amazon.com/gp/product/B00NQGP42Y/ref=as_li_tl?ie=UTF8&camp=1789&creative=9325&creativeASIN=B00NQGP42Y&linkCode=as2&tag=bytesblog-20&linkId=SNRBFHRRACFBTYJI"><img style="float:left;margin-right:25px" border="0" src="http://ws-na.amazon-adsystem.com/widgets/q?_encoding=UTF8&ASIN=B00NQGP42Y&Format=_SL250_&ID=AsinImage&MarketPlace=US&ServiceVersion=20070822&WS=1&tag=bytesblog-20" ></a><img src="http://ir-na.amazon-adsystem.com/e/ir?t=bytesblog-20&l=as2&o=1&a=B00NQGP42Y" width="1" height="1" border="0" alt="" style="border:none !important; margin:0px !important;" />
Apple is perhaps the biggest “silo” project out there.   They do just about everything themselves, including chip design, computers, operating system, applications, and services.  What makes Apple unique and valuable to me is how well all of their systems are integrated and complement one another.  

Ever try to use an iPhone with a Microsoft Sync car and a Linux desktop PC?  Despite compatibility on a wide number of standards and support for basic functionality, the experience is terrible.   Now compare that to using an iPhone with an iMac and CarPlay.  The difference is night and day in the seamless transitions between phone, tablet, computer, and car.   This is made possible by tight integration.   

Crypto currencies are already very hard to use.  Right now about the only standard widely used among crypto currencies is the elliptic curve key space.   A Bitcoin public/private key is compatible with BitShares and most Bitcoin clones.  This has made some integration possible such as share drops, [crowd funding]({% post_url 2014-12-26-Stop-the-Crowd-Sales-Long-Live-Crowd-Funding %}), and [gateways]({% post_url 2014-12-18-Benefits-of-Being-a-BitShares-Gateway %}).

What happens when you combine a bunch of immature, hard to use, systems?  You get an impossible to use system.    This is why BitShares and everyone else is so focused on their own thing right now.  There market is demanding easy-to-use crypto and achieving easy-to-use at the same time as standardization across many projects is an order of magnitude harder than keeping it all within a “silo”.   

## Standardization is for Mature Markets 
Calls to standardize on one ID system, one reputation system, one smart contract language, or one distributed storage solution are premature.   The market will evolve toward standardization after it has let darwinian survival of the fittest project find out what the best approach is.   

I personally don’t like the Etheruem approach.  Storj and MaidSafe are both sub-optimal solutions compared to my own designs which I was working on prior to starting BitShares.   There is so much room for innovation that no one should be compromising for the sake of standardization this early in the game.

## Don’t Question the Free Market 

When you have a free and open market the incentives are already aligned for some player to rapidly integrate the work of others and make a profit, if there is a profit to be made in doing so.   We are fragmented because the market is so young that each team has a realistic chance of “winning it all” or at the very least walk away in the top 3.     Currently there are only 4 or 5 real block chain technologies out there:  Bitcoin, Ripple, BitShares, Nxt, Ethereum, and MaidSafe.   Everyone else is a clone with slight modifications.    Each one of these has a market segment and can all co-exist very profitably. 

Integration will occur naturally after the winners are so entrenched with network effect that few startups would even consider attempting to compete.    How many search engines were there when Google was founded?   How many people would consider starting a company to compete?   Once the technology is mature and there are entrenched leaders, then the level of innovation required of a competitor is much higher.   At that point in time you will see startups prefer to integrate rather than compete.      

With BitShares I believe that an integrated and seamless user experience is of higher priority than compatibility with a dozen half baked crypto projects.   Everything we do is open and the BitShares block chain can fund 101 developers to integrate with all kinds of projects if there was any interest from the community to do so.   

## Conclusion

I think Vitalik is right about the need to drop the winner-take-all mindset and embrace a friendly competition.   We can all win in our own way.   Over the next couple of years you will see many fragmented technologies each competing for market share, but eventually everything will consolidate down to a top 2 or 3 in each market.    

I think you will never see a single winner for the simple reason that everything has its opposite.  We have Republicans and Democrats, VISA and MasterCard, Pepsi and Coke, Apple and Microsoft.   Based upon todays landscape it is very likely that any project that can maintain funding and momentum will end up in the top 3.   

So lets all respect each others projects and recognize and value our differences.  There is no need to be hostile or to fear each other.    Like all things in life, we should embrace love over fear and when we do that we will turn hostile competition into friendly competition and everyone will win.   


