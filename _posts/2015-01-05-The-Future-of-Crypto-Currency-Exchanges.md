---
layout: post
title:  "The Future of Crypto Currency Exchanges" 
author: "Daniel Larimer"
categories: article 
---

I started BitShares in response to Mt. Gox having its US bank accounts seized.  Since then a number of major crypto currency exchanges have been hacked or shutdown.  Just this weekend my favorite bitcoin exchange, [Bitstamp](http://bitstamp.net), had its hot wallet [compromised and has temporarily suspended service](http://www.cnbc.com/id/102309754#.).   Time and again we are reminded that so long as we are relying on 3rd parties to hold value on our behalf our wealth is at risk.   Today I would like to present a better approach to crypto-currency exchange.

Imagine if you could buy and sell a crypto currency without any direct exposure to counter party risk.  Imagine if the fees were lower and there were no withdraw limits.   Imagine if you could trade against all currencies including gold and silver.   Imagine if there was one order book with the best liquidity the market can offer.   This is possible today with BitShares, but it is currently one of the best kept secrets in the crypto-currency space.

## Roles of an Exchange 

Before diving into how crypto currency exchanges will work in the future, lets review the roles that traditional exchanges perform today.

1. Receive crypto-currency and issue IOU
2. Receive fiat and issue IOU
3. Process an Order Book 
4. Redeem IOUs 

Each of these roles has a high degree of trust and direct counter-party risk because at all stages you are transacting with an IOU from the exchange.   To get the best liquidity and lowest spreads requires a large and active order book and this means that most people gravitate toward a few core exchanges and everyone is exposed to the same <a href="http://www.amazon.com/gp/product/1466516453/ref=as_li_tl?ie=UTF8&camp=1789&creative=9325&creativeASIN=1466516453&linkCode=as2&tag=bytesblog-20&linkId=Q6REXYQWLFA4QA23">Counterparty Risk</a><img src="http://ir-na.amazon-adsystem.com/e/ir?t=bytesblog-20&l=as2&o=1&a=1466516453" width="1" height="1" border="0" alt="" style="border:none !important; margin:0px !important;" />.  BitStamp is an example of one of the highest volume Bitcoin exchanges and I have thousands of dollars locked up on Bitstamp that are completely inaccessible at the moment because its service has been temporarily (I hope) suspended.

There is a large time delay associated with moving money into or out of an exchange, which means that traders must keep their funds on the exchange.   This magnifies the amount of risk to users of the exchange.   It also magnifies the risk to all users in the Bitcoin ecosystem.   Whenever there is a large security breach it results in significant sell pressure from both the thief looking to cash in their loot and from regular users hoping to sell before the thief.  

## Centralization Compromises Privacy 

Crypto currencies depend upon a public ledger which makes privacy challenging because everyone can see every transaction.   Bitcoin gives every user one or more account numbers, and that gives many people a false sense of security.   People assume that as long as no one knows your account number and you use a new account number with every transaction that no one can tie all of your Bitcoins to your real life identity.  

This is where the large centralized exchanges become a problem.   In order to comply with government regulations they must know everyone they do business with.  Since almost every other Bitcoin transaction flows through an exchange, the exchange learns who everyone is and can start to track who is doing business with whom.    [Coinbase is already closing accounts](https://www.cryptocoinsnews.com/coinbase-bringing-big-brother-bitcoin-accounts/) based upon who you do business with after withdrawing your Bitcoins.     

If we want to have even the slightest bit of privacy we need to divide the exchange functionality among hundreds of parties who are unlikely to collude to compromise identity.   This is not economically practical today because the exchange order book creates market incentives that naturally tend toward centralization in just a few exchanges with the vast majority of market share. 

If privacy concerns you then I recomend my article on ["How to maintain Privacy with BitShares"]({% post_url 2014-12-23-How-to-Maintain-Privacy-with-BitShares %}).

## Separation of Powers

There is no reason why the same entity needs to be responsible for issuing IOUs and for processing the order book.  It is only because these two roles are combined that we have a tendency toward centralization in the Bitcoin exchange space.  If we want to create a decentralized exchange then the first step is to move the order book on to the blockchain where everyone can see it.

Exchanges should become mere gateways that receive USD and issue GatewayUSD on the blockchain.  Later they receive GatewayUSD and then execute a wire transfer.   They will make their money entirely on transaction fees and not from a percentage of market fees.   Check out my earlier [blog post about the benefits of becoming a BitShares gateway]({% post_url 2014-12-18-Benefits-of-Being-a-BitShares-Gateway %}).  

The blockchain will allow users to trade BitstampUSD against BitfinexUSD in order to easily move funds from one gateway to another.  Users can even trade BitstampUSD against BitstampBTC or BitstampUSD vs BitfinexBTC.  

Unfortunately, simply moving the order book to the blockchain is not enough because the market will naturally centralize around a few gateway IOUs and the markets for them.  BitstampUSD is not fungible with BitfinexUSD because they have different trust profiles and regulatory considerations.   Any of these IOUs are subject to default just like the IOUs that currently exist on the exchanges' internal databases.   What we need to do is move the trust from individual issuers to the blockchain.

## Collateralized Blockchain IOUs 

The heart of BitShares is the [BitAsset]({% post_url 2014-12-18-What-are-BitShares-Market-Pegged-Assets %}) system which enables the creation of 300% collateralized IOUs from the BitShares network.   A BitUSD has all of the properties of Bitcoin combined with the price stability of the US dollar.  At any point in time you can sell a BitUSD for about 1 dollar worth of BTS.  If at any time the value of the collateral falls below a certain point the blockchain will automatically buy back the BitUSD with a dollars worth of BTS.

When you hold BitUSD the value of your holdings will remain pegged to the dollar so long as BitShares itself has reasonable volatility.   When I say reasonable, I mean it can handle greater volatility than Bitcoin has ever seen in its life time.   The price of BitShares would have to fall to less than 1/3 its starting price in less than 24 hours and then stay there.   No legitimate, widely adopted crypto-currency has ever seen that kind of price movement.  This means that BitUSD is secure against just about everything but an unfixable software bug in the BitShares protocol itself.    By the time BitShares matures to the level Bitcoin is at today you could expect the probability of that kind of bug to be similar to Bitcoin having that kind of bug. 

If you want know more about [how our market pegged BitAsset system works]({% post_url 2014-12-18-What-are-BitShares-Market-Pegged-Assets %}) then checkout my detailed article on the subject.

## Global Unified Order Book

Once the market adopts BitUSD and BitBTC as more reliable and decentralized alternatives to BitstampUSD and BitfinexBTC you will see the majority of trading volume move toward BitUSD vs BitBTC.    The only time someone would want to move from BitUSD to BitstampUSD is when they are in the process of withdrawing to the traditional banking system.  

The impact of a global unified order book is to end all arbitrage opportunities, minimize spreads, and maximize liquidity.   By having the trades executed on the BitShares network you also eliminate high-frequency trading and front running.   High frequency trading and front running depend upon centralized exchanges with high volume and deep markets.   If the vast majority of trading activity were to move to a decentralized, trust-free exchange then the remaining centralized exchanges would be much less appealing to high frequency traders.  

## Lower Market Fees 

BitShares charges per-transaction fees, just like Bitcoin.   Currently these fees are less than $0.01 which means that you could place an order to convert $1000 to 3 BTC for just $0.01.  If you were to do the same thing on Bitstamp then they would charge you 0.5% or a total of $5.  For this single trade BitShares is 500x more cost effective.   It also means that traditional exchanges have wider spreads because the exchange fee becomes built into the spread.  For all practical purposes the fees saved here should cancel out any extra fees associated with the BitUSD / GatewayUSD spread.   

## BitUSD to USD Gateways 

Many gateways will prefer the low risk approach of one-for-one redemption and will simply allow the GatewayUSD to float against BitUSD with a small, but variable, spread in the market. Users would end up paying a small variable conversion cost as they exit from BitUSD to fiat USD through GatewayUSD.  

On the other hand, many users will want a direct conversion from BitUSD to fiat USD.  In this mode of operation the gateway takes care of providing all of the liquidity within a fixed percentage transaction fee.   The gateways will then compete on offering the lowest possible spread.  

Once this happens then BitUSD is effectively as good as USD with a small fixed conversion fee.  This fee will likely be no more than the withdraw and deposit fees that current exchanges charge.  BitShares will be a fully operational exchange with many banking partners and no limits.   At no point in time will user deposits ever be subject to default or confiscation by an exchange or gateway.   A truly decentralized exchange will have been realized and the original vision of BitShares complete.  

## 2015: The Year of the Decentralized Bitcoin Exchange

I recently did an interview with Max Wright of [BitShares.TV](http://bitshares.tv) about this topic that is worth checking out.

<iframe width="620" height="349" src="//www.youtube.com/embed/TtCVRIwcBYU" frameborder="0" allowfullscreen></iframe>

