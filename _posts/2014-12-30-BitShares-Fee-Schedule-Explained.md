---
layout: post
title:  "BitShares Fee Schedule Explained"
author: "Daniel Larimer"
categories: bitshares
---
There are only two constants in life, death and bank fees.   Today I am going provide some much needed clarity about what types of fees BitShares charges, why they are charged, and how they can be paid.  

From a high level there are two kinds of fees, deterministic fees defined by the protocol, and variable transaction fees set by the delegates.  In practice delegates can raise, but not lower, the deterministic fees with unanimous consent of the delegates.

## Variable Transaction Fee

The most common fee paid by every single transaction is the variable transaction fee.  This fee is not mandatory nor enforced at the blockchain validation level.   In theory the fee could be 0 BTS, assuming there existed at least one delegate that was willing to process your transaction.  

Variable fees are up to the discretion of delegates which must maintain shareholder approval.  The primary purpose of these fees is to cover the actual costs of propagating, validating, and storing the transaction on the blockchain.    The minimum amount you can get away with paying is determined by the delegate that charges the least; however, for best performance you should pay an amount equal to the delegate that charges the most.  

As of December 2014 the default minimum fee required by the delegates is set at 0.1 BTS which is a fraction of a cent.  The default fee specified in the wallet is 0.5 BTS which is about 1 cent.    The amount paid by the wallet is configurable, but the default is more than necessary so that it is future proof.   

These variable transaction fees can also be paid in BitAssets such as BitUSD, BitGOLD, and BitCNY.    If fees are paid in BitAssets then the delegates require twice the fee.  In other words if they require .1 BTS normally, they will require .2 BTS worth of BitUSD.   Delegates use the built in price feed for the BitAsset to determine the conversion from BTS to BitUSD.   Once again, this fee and ratio is ultimately up to the delegates to decide.   The reason for charging more for a BitAsset is to incentivize users to hold some BTS in their wallet for paying fees and because we can charge more for the convenience afforded by being able to use BitAssets directly for fees. 

Delegates can publish their fee expectations as part of the public data associated with their account.  In the future wallets will be able to use this published information to automatically select the proper fees for the user.   

## Transaction Relay Fee 

When transactions are broadcast across the network all nodes have an opportunity to vote on the fee.   Generally speaking this fee is identical to the variable transaction fee in all cases except when there is network congestion.  If the network becomes flooded with transactions then the peers will automatically start increasing the relay fee.   For all practical purposes, this particular fee doesn’t need to be considered and a user can simply wait for an opportunity to broadcast their transaction at the normal fee. 

## Delegate Registration Fee   

Delegates are special accounts that may be approved by shareholders to produce blocks and optionally receive pay.   Delegates can set their pay rate as a percentage of the maximum block reward which is 50 BTS.   The delegate registration fee is equal to two weeks of pay at the requested pay rate or 59,881 BTS for a 100% pay delegate.   At the time of this writing that is about $1000.    This particular fee must be paid in BTS.

The primary reason for the fee is to discourage anyone who doesn’t believe they can gain shareholder approval from even attempting to run.   This will act as a first level of screening and prevent everyone from attempting to get votes.   It is also a security measure that gives shareholders an opportunity to vote someone out within two weeks and avoid being diluted.  After two weeks of proven performance an elected delegate breaks even.   If a delegate is never elected then the fee goes to support the network.

This fee must also be paid any time an account is upgraded from a regular user account to a delegate account.  

## User Issued Asset Registration Fee

User Issued Assets are a powerful feature that allows anyone to create a token that can be traded on the internal exchange.  Each token is allocated a unique trading symbol such a BTS, USD, etc.   Good trading symbols (those of 5 characters or less) are of limited supply; therefore, the network charges 500,000 BTS (about $7500) to reserve.   The intent is to reserve the good trading symbols for businesses that aim to make a profit using the symbol.     Symbols that are between 6 and 8 characters are available at the cheaper rate of just 500 BTS ($7.50) so that users can use them for personal use or unprofitable applications.  

When dealing with user issued assets, users must pay the variable transaction fee using BTS or a BitAsset. 

## Market Fees 

The internal market collects fees from order matching anytime there is an overlap in the bid / ask price.  This can be thought of as the blockchain acting like a middle man between two people who don’t know what the other is offering.    First the blockchain buys the asset from someone selling it cheap, then the blockchain sells the asset to the individual buying it at a higher price.   The blockchain is the counter party to all transactions and the profits it earns on the overlap are used to grow the BitShares network.  

When I describe this system to people I state it simply: “Everyone gets what they asked for, so no one can complain”.   Taken from this perspective, a user pays no fees for market transactions other than the normal variable transaction fee charged on every transaction.  On the other hand, because the network is completely transparent a user would notice an opportunity cost associated with not perfectly matching a counter offer.   

The purpose for this order matching algorithm and the resulting fees is that if the network did not collect these fees, then individuals and especially delegates observing the network could easily front run orders.  Front running has the same effect on the end user: they get what they asked for.  The difference is that who ever happens to be the fastest and in the right place at the right time gets to keep the profit rather than the network as a whole.   

As a side effect this algorithm also minimizes attempts to manipulate the market by walking the entire order book in a single block.   Clients can still manually match orders to completely eliminate the market fees, but it will require them to match exactly one order every 10 seconds rather than all at once.   In effect, the market fees act as a speed and convenience tax and gives the market time to respond to large moves.    

If there are any market fees collected on User Issued Assets then they are returned to the issuer.  This provides issuers an incentive to create assets that are actively traded on the blockchain.

## Short Interest Fees

Users that would like to leverage their BTS positions can borrow BitUSD at interest to enter a short position.  The interest rate is set by the user and will affect the priority their short order has at getting matched.   

## Margin Call Fees 

If a short position runs low on collateral (BTS), then the network will automatically cover the users position using their collateral.  If there is any collateral left over then 5% will be kept as a fee and 95% will be returned to the owner of the short position.   This fee is designed to encourage pro-active maintenance of margin and minimize the impact and predictability of when shorts will cover. 

## Where Fees Go

All fees paid in BTS are accumulated into a fund that is gradually paid out to all delegates over two weeks.   When a delegate produces a block they are entitled to a percentage of the fund which is then adjusted by their delegate pay rate.  A delegate with 100% pay will receive the full amount, where as a delegate with 0% will burn the full amount they are entitled to.   When BTS is burned this is similar to returning the value to the shareholders.     We can therefore summarize it as all BTS fees are paid to delegates or returned to shareholders.

All fees paid in BitAssets are added to a fund which is slowly paid out as yield to BitAsset holders.  The markets for BitAssets collect their fees in the BitAsset to maximize yield on the BitAssets.  

Everybody would love a system that was free to use, unfortunately nothing is ever free nor can it be.   Scarce resources must be rationed to prevent abuse and so fees are necessary.


