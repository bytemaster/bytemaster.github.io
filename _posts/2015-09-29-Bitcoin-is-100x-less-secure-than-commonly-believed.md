---
layout: post
lang: en
author: "Daniel Larimer"
title: "Bitcoin is 100x less secure than commonly believed"

categories: update
sharing: true

---
The reason proof of work is considered secure is because it is more profitable to join the honest network than to attempt to attack it.   The more money you can earn mining for the honest chain, the more costly it becomes to produce an alternative chain.  At the core of this security is the concept that all actors pursue profit first and that any rational attack will only occur if it is profitable to do so.  

Each day the Bitcoin network pays out 25 BTC ($6000) every 10 minutes or a total of $864,000 per day in rewards.   The cost of claiming those rewards approaches 100% of the value of those rewards as market competition increases.   For the sake of this article we will assume a net profit of 5% which means that the cost to gain 51% is $864,000 x .51 x .95 or about $420,000 per day.   

We will assume an attacker wants to gain control over the network so that they can censor transactions and raise fees.  The assumed cost of this attack is $420,000 per day and this is the value that is commonly believed.

The reality is that 10 mining pools collectively control 95% of hash power and 3 pools control over 51%.   Using the profitability metric, the security of the blockchain depends upon whether or not it is more profitable to be a censorship free mining pool or to start censoring transactions.   Assuming all mining pools earn a 1% commission on all blocks mined (ignoring expenses) then collectively 51% of the mining pools are earning $4200 per day (about $175 per hour).  In reality many mining pools charge no fee and are operating at a loss. 

This means that the cost to compromise 51% of mining pools which are driven only by profit is similar to hiring a very talented hacker and vastly cheaper than hiring a team to build and maintain an alt-coin to pursue your vision.   

The first argument everyone makes is that miners would switch pools if any pool started censoring transactions.   This may be true, but to keep an objective measure of security we must assume they would only switch if it were profitable to do so.   Considering profit margins are already minimized by free-market competition it will only take a small amount of negative mining to make any pool unprofitable.  A negative miner is one who joins a pool, collects their share, but never returns a wining hash.   To wipe out a 5% profit margin in a pool requires negative mining with 5% of the pools hash power of which you get 95% of your costs back so 0.25% or $1000 dollars per day ($42/hr) is the cost to make mining on 51% of the pools unprofitable.   

So far we have a total of $5200 dollars per day as the cost to make it more profitable to join the attacker (by doubling your pool’s income) and unprofitable to resist the attacker (by eliminating all profit from competing pools).      

The only option that remains is to close all public pools to eliminate the negative mining attack, but that results in effectively eliminating the ability of “miners” to switch pools.  It also increases the variance among the smaller private pools which reduces the pools margins.   Once this happens the $1000 per day that went to negative mining can now be redirected toward subsidizing mining on the censoring pool.  Miners driven to maximize profit and with no long-term incentive will support this pool which will raise the difficulty and once again cut into the profits of the private pools.  

Mining must be pooled in some fashion to maximize profitability and minimize variance which means that market forces will concentrate hash power.   Once hash power is concentrated the attacker only needs to spend money proportional to the profit margin of the miners and not proportional to the absolute cost of the mining.    Market competition drives the profit margin toward 0 which ultimately drives the cost of attacking the network relative to the size of the network toward 0.   

The proposed attack assumes $5000 per day as the cost to co-opt miners into censoring transactions and thereby controlling the future of the network AND controlling transaction fees.   Such an attack would have the predictable side effect of causing the BTC price to fall.

The existence of exchanges with the ability short-sell BTC means that an attacker could fund the vast majority of their attack with the proceeds of short-selling BTC.   Assuming the price of Bitcoin fell by 50% as a result of such an attack the individual doing the short sell could double their money.  

At the end of the attack the attacker will have gained control of the BTC network and the vast majority of its network effect.   If your goal was to create a business around a crypto-currency then coopting even 10% of BTC’s network effect at a profit would be a major win.

So in conclusion, the cost to attack Bitcoin based solely on profit-motive game-theory is closer to $5000 per day than the $500,000 per day that is commonly believed.  This exists because proof of work is dominated by realtime electricity costs with small margins.

## Proof of Stake Alternatives 

In proof-of-stake systems the cost to attack the network is proportional to capital held in the network.  This means that you cannot use shorting of the proof-of-stake coin as a means to cover the cost of the attack.   Any money you gain from your short position, you will lose from your long position used to virtually mine blocks. 

Under Delegated Proof of Stake it becomes practically impossible to buy enough stake to unilaterally vote for the witnesses whom produce blocks.   The witnesses can be thought of like elected mining pool operators.   The cost of compromising a profit-seeking witness is like the cost of compromising a profit-seeking mining pool operator.  The more a witness makes by not censoring the more you must pay them to censor.   For the sake of this discussion we will assume that the attacking witnesses will refuse to include transactions that would vote them out of power.  

If we assume witnesses charge the same amount as a mining pool as a percentage of market capitalization then from an economic perspective, the cost of compromising 51% of the witnesses would be identical to the cost of compromising 51% of the mining pool operators and that the resulting network security would be equal.

Delegated Proof of Stake 2.0 implements an extra sanity check that requires 2/3’s of all witnesses for the chain to continue adding new blocks.  This means that to co-opt the network via censoring without killing the network would require compromising 2/3’s of the witnesses.  If you compromise less then either you will be unable to censor voting or the chain will halt due to low participation and require a hard fork or manual checkpoint to continue.  

There remains one key difference between mining pool operators and witnesses.  Witnesses are vetted for their loyalty where as mining pool operators are only vetted by their ability to gain market share.   The cost of compromising an each individual is different.  Some individuals cannot be bought at any price, others sell out cheaply.    One extremely loyal witness can be more secure than 10 profit-seeking opportunists. 

When it comes to bribes and market-driven attacks, having more high-quality, vetted witnesses is much more secure than having fewer self-appointed mining pool operators because the cost of buying defection is higher.

The last remaining attack vector is that of coercion and for this we will simply assume that the cost to coerce all individuals is the same and therefore, the more people you must coerce the more expensive and ultimately more secure the network becomes.  Here the comparison becomes trivial: 3 mining pool operators vs potentially unlimited number of witnesses.

So next time someone suggests that Bitcoin is too expensive to attack, think again.  The only reason Bitcoin has not been attacked is because there is not a solid business model around censoring transactions and therefore a hostile takeover does not make sense.   Once someone develops a business plan that can benefit from gaining control of Bitcoin’s block production it will be done and no amount of hash power will be able to prevent it.
  



 
