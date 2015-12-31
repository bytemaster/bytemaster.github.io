---
layout: post
title:  "Why I like Ethereum"
categories: blog
author: "Daniel Larimer" 
---

I have said many negative things about Ethereum in the past, but today I would like to change that. 
Due to recent disputes within the BitShares ecosystem I have come to appreciate a certain qualities of
Ethereum that the BitShares community could learn from.

<!--more-->

Over the past several months I have heard the following complaints over and over:

  1. Only Cryptonomex can add features to BitShares
  2. There is no documentation 
  3. Core developers should focus on X
  4. BitShares is centralized 

All of these complaints are unfounded, but the perception remains. There is ample documentation and plenty of 
examples and community support. Anyone who knows C++ and is able to learn the Ethereum scripting language could just
as easily learn our API and add features.  Like most things in life, perception matters more than reality.  

## Smart Contracts are like Fee Backed Assets 

If BitShares were like Ethereum then it would have a programming language that would allow anyone to
add new features without having to "ask" permission of the stakeholders.  These new features would be in the form of
new smart contract(s) that many people could use and these contracts could charge their users a fee
for using them. This fee could then be used to buy back an asset created by the smart contract itself.

In other words, Ethereum already incentivises developers with Fee Backed Assets.

There are many reasons why Graphene doesn't have a smart contract scripting environment including:

   1. Performance - Ethereum is currently performance-limited to 20 transactions per second
   2. Complexity - It is very difficult to cover all corner cases
   3. Tools - supporting a virtual machine is only part of the problem, developer tools are needed too.
   4. Libraries - a new programing language is nothing without robust standard libraries 

All of that said the benefits Ethereum gains by being neutral to application content is a breath of fresh
air compared to the constant bickering over what feature to add to BitShares next or whether that feature should
even be allowed on the BitShares blockchain. 

If someone wanted to create a gambling application on Ethereum, they could.  They could also implement a mutual aid society on Ethereum.

## BitShares should be Neutral  

In theory there is no reason why BitShares couldn’t become just as open and welcoming to developers as Ethereum.  Developers just need to have confidence that if they work on a new smart contract that it will be accepted by blockchain after reasonable peer review.  The peer review will check for neutral things like:

  1. Unit tests for every scenario 
  2. Non deterministic behavior (floating point)
  3. Proper accounting (no printing of money)
  4. Proper permission validation (no unauthorized transfers)
  5. Proper performance (no unbounded computations)

Anyone can create new smart contracts for BitShares today.  There is ample documentation and examples within the code and a community of developers ready to answer any questions those developers may have. A simple tutorial could be drafted on how to write contracts for BitShares. 

## Automated Peer Review 

One of the benefits of Ethereum is that they have automated most of the peer review by sandboxing contracts and their data. It isn’t possible for one smart contract to corrupt the data belonging to another smart contract. This means that users only need to concern themselves with the validation of the new contract’s internal behavior. 

There are many ways to perform sandboxing. Ethereum does it through a virtual machine with private data, but BitShares could achieve much of the same level sandboxing by limiting Smart Contracts to a well defined API.  This API would restrict write access to any data not managed by the smart contract.

## Ethereum VM on BitShares

I would actively support a FBA to integrate the Ethereum VM into BitShares. Done properly this would have 
significant advantages over the current Ethereum blockchain. I would make the following minor modifications to the
EVM's implementation:

  1. I would keep everything in memory.  Level DB is the bottleneck on Ethereum's performance.
  2. I would eliminitate the merkle tri-graph.  If the VM is determinsitic this is redundant and expensive calculation that is only required for very specialized applications. 

## Conclusion 

Ethereum has solved some of the biggest issues facing BitShares today.  Meanwhile, BitShares has solved some of Ethereum's biggest issues. 
The BitShares community would be wise to learn from the good aspects of Ethereum and adopt a default position of
accepting any and all smart contracts / hard forks are proposed, funded, and peer reviewed.  We must drop the notion that
only *one thing* can be worked on at any given time and instead embrace the notion of BitShares as a platform and BitShares as
a community.  

I will do my part to provide guidance to new developers along with tutorials. Will you do your part of welcoming any and all development on BitShares?


