---
layout: post
lang: en
title:  "The Value of DevShares"
author: "Daniel Larimer"
categories: 
    - update
---
Block chain technology is constantly evolving and while Bitcoin appears content to stand still, we feel BitShares needs to be more dynamic so it can evolve with the market.   Stability and predictability are core features of any block chain and any interruption in service can have a dramatic effect on the market.

<!--more-->

<img style="float: right" src="/media/upgrade_comic.png" width="400px">

There is a saying that no upgrade goes unpunished.  And despite the best efforts of large companies such as Apple, they still have the occasional bug introduced by an upgrade.  All of the testing in the world is unable to find every bug or test every environment.

My fellow developers and I face a similar challenge with BitShares.   We have test cases, unit tests, regression tests, test networks, and peer reviews, but they are unable to fully cover all potential bugs.    

Perhaps one of the most difficult bugs to track down are bugs in the upgrade process itself.  When we migrate from one version of BitShares to another there is often some small amount of glue code that manages the transition from one set of block chain rules to another.   The only place this glue code can be tested is on the real network.    

Some bugs only show up on user machines, on some operating systems, or worst of all only when the right combination of machines each running slightly different versions of our software.  The odds are against our developers being able to find everything, yet the cost of bugs is higher than ever.

## Introducing DevShares

DevShares is our effort at simulating the conditions of the real BitShares network as closely as possible so that we can test every upgrade throughly prior to upgrading BitShares.  To do this we need a live network, with delegates around the world upon which BitAssets are trading.  We need a network that has real value and real users who are experimenting with every proposed update.

In many ways BitShares has been operating as a live development network over the course of the past five months.  We have been upgrading it every couple of weeks and from time to time one of our upgrades goes wrong and we have to follow it with a rapid patch.  This process has been frustrating for users and our business partners who have a difficult time keeping up.

DevShares is designed to off load a lot of the upgrade uncertainty from the BitShares network; therefore, DevShares will be identical to BitShares in almost every respect except for the block numbers that upgrades occur at.    Once DevShares reaches a stable and tested version, we will migrate the code to BitShares and keep the changes to a single number in a single file: the block number at which the upgrade should happen.

## Why DevShares Have Value

Considering the risks of an upgrade going poorly and the potential for a rapid update cycle, why would anyone value DevShares?   It boils down to one simple reason, we are not the only ones who need a test network.  Our exchange partners, merchants, plugins, block explorers, etc. all need a solid testing network.   If you are going to test then you will need to pay some transaction fees on the DevShares network.    If you want to beta test your product on a live network with real users prior to the feature being adopted by BitShares proper, then you will want DevShares.    

This is no different than early Bitcoin test networks that started to gain value as an alt-coin.  The Bitcoin developers had to modify the block chain in such a way as to prevent it from being imbued with value by the market.     

Unlike the Bitcoin test network, we really do need and want DevShares to have some real value because only through having real value will a distributed user base actively test it; especially the market features.   You cannot test BitAssets throughly unless the collateral has value.

## Delegate Training Ground
DevShares provides a training ground for new delegates who may one day hope to get elected on the BitShares network.   Most delegates on the BitShares network should be expected to also host at least one node on the test network.  

All delegates can then test and debug their upgrade process on the DevShares network and help find and report issues.   If delegates are experimenting with automated fail overs or other infrastructure they will want to make sure it doesn’t inadvertently harm the network.

The DevShares network will have lower value and thus will pay delegates 500 DVS (vs 50 BTS) per block which will result in a much higher initial dilution (up to 60% per year).  This pay will help compensate delegates that participate in testing and generate some spare DVS that they can distribute to those who need it.

## Community Driven
We would like the DevShares network to be a place for the community to drive adoption and marketing.   Give away threads, free samples, etc. open the door for our community to try out new systems without risking the BitShares network directly.    The core developers will be looking to the community to help test every version, to practice their trading skills, and otherwise use the network.    

We will probably offer bounties for bugs found on the DevShares network and this will help everyone.    

## BitShares grows Up

DevShares is the first step toward BitShares growing up to act like a mature production ready environment that people can trust.   The very existence of DevShares and the public testing that it represents will help the market gain confidence in upgrading the BitShares network.  

## Initial Allocation 

<span style="text-decoration: line-through"> The network will be initially allocated as 2 billion shares divided equally among AGS, PTS, and BTS holders as of the December 14th snapshot date.   An additional 50 million vesting shares will be allocated the same was as the 500 million vesting shares in BTS.   These vesting shares are there so that we can throughly test all operations that deal with vesting balances.</span>

Update 1/7/2015:  We have relaunched DevShares with a new allocation.  Please see my post titled [DevShares Reloaded]({% post_url 2015-01-08-DevShares-Reloaded %}) for more information.

## Expectations 

DevShares will undoubtedly be listed on exchanges and many gateways will probably pop up to support the network.  It is important that everyone who is participating in the DevShares network understands that all user issued assets on the DevShares network should be “contract free” and if a bug happens to result in a massive loss to the issuer, the issuer is free to take what ever action they deem appropriate to make people whole (or not).   Any gains or losses as a result of a bug on the DevShares network are part of the system and no one shall be held responsible for any losses.  No one can execute a scam on the DevShares network because all such scams are deemed to be legitimate voluntary choices in a contract free world.   

It is important that you have your expectations set right here.  Exchanges may freely walk away with your DevShares deposits without any moral issues.  When you transfer your funds to the exchange they become the exchanges and are not an IOU.   If an exchange loses your transaction or suffers a loss due to a bug or double spend then that is just your luck.  It is a development network and all operations and transactions are inherently a gamble.

I feel this kind of disclaimer is necessary to encourage exchanges to participate in our development network without fear of any liability.   Some people will have a hard time managing their expectations, but it will be up to the community to remind them of the social consensus on the DevShares chain that there are no scams, “theft” is legitimate, and trust is a gamble.   

The DevShares network will launch this week and we will start using it for all proposed upgrades to the BitShares network.   If you would like to experiment with our latest beta features then DevShares is the place to be. 



