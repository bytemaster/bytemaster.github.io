---
layout: post
title:  "How to build a Decentralized Application without Fees"
author: "Daniel Larimer"
categories: article

---

Blockchain technology currently depends upon transaction fees to prevent spam. These fees suffer all of the known problems with microtransactions that prevent blockchains from being used for necessary low-value transactions. Truly decentralized applications must offer users the appearance of free transactions if they wish to compete with their centralized alternatives. This paper outlines an approach to eliminate the need for fees and thereby enabling a wide range of previously untenable decentralized applications.

## The Problem

Blockchains are decentralized networks where all transactions are broadcast to all peers. Every so often a block is produced that includes some or all of the pending transactions. All blockchains must find a solution to prevent malicious users from consuming all of the available network capacity with worthless transactions. These worthless transactions can prevent other valuable transactions from being processed and ultimately destroy the network.

The solution adopted by most blockchains thus far is to charge a minimum transaction fee. A fee worth just a few cents is enough to make attacking the network expensive and unprofitable. While this approach solves the spam problem, it introduces new problems. Imagine solving the email spam problem by introducing a small fee on every email; people wouldn’t use email. 

### Micropayments Don’t Work 

The fundamental problem with charging transaction fees is that micropayments don’t work, especially for low-value user actions. When a fee is charged on every transaction, it limits the types of transactions that a decentralized network can process. Regardless of how rational the argument for the necessity of fees, users still hate the experience of being nickeled and dimed for everything that they do. 

Imagine if all of the websites we use every day charged us a fee every time we modify our accounts by changing the password. Users expect certain things to be free. Requiring users to make a decision on whether or not an action is worth a small fee creates anxiety that causes users to leave.

> A transaction can't be worth so much as to require a decision but worth so little that that decision is automatic. There is a certain amount of anxiety involved in any decision to buy, no matter how small, and it derives not from the interface used or the time required, but from the very act of deciding.
>
> Micropayments, like all payments, require a comparison: "Is this much of X worth that much of Y?" There is a minimum mental transaction cost created by this fact that cannot be optimized away, because the only transaction a user will be willing to approve with no thought will be one that costs them nothing, which is no transaction at all.
>
>  -- [Clay Shirky](http://www.openp2p.com/pub/a/p2p/2000/12/19/micropayments.html)

In the world of financial payments small fees are acceptable because the value of the transaction is extremely high relative to the fee charged. The world of potential blockchain applications is far greater than just financial payments and includes many necessary transactions for which fees are unacceptable.

Systems like BitShares, Nxt, Ripple, Counter Party and Stellar all allow users to place limit orders on the blockchain and all of them charge users a small fee to perform this action. Later if the user wishes to cancel their order, another fee is charged.   Systems like Ethereum take micropayments to a whole new level: charging per calculation.  All of these systems struggle to attract new mainstream users for the same reasons that a decentralized search engine would struggle to attract users from Google if it charged a small fee for every search. It doesn’t matter how good the service is, people expect certain things to be free. This is true even if a user ends up paying more overall under a different fee structure.

### Barrier to Entry 

Any fee creates a barrier to entry for new users. Before someone can experiment with Ethereum they must acquire some ETH tokens. Anyone wanting to build a decentralized application on Ethereum must pass on the cost to their customers.  Buying a crypto currency is not an easy task and rarely makes sense for amounts less than $10. This means that new users wanting to try out a new decentralized application must first be convinced to part with $10. 

### Changing Fees

Over time a network must adjust fees. This can happen either due to an increase in the value of the token or due to a surge in capacity. Users like predictable fees and guaranteed service. While it is possible to dynamically adjust fees during times of heavy use, the result is a poor user experience.    

### Sybil Attacks

Centralized websites prevent spam through rate limiting and some form of ID verification. Even something as simple as [reCAPTCHA](https://www.google.com/recaptcha/intro/index.html) is sufficient to limit the creation of fake accounts. If someone abuses their account then centralized websites are free to block the account. 

In a decentralized system there is no direct way to ban users nor centralized provider able to host a reCAPTCHA and enforce rate limiting of accounts. In fact, the inability to censor users is a main selling point of blockchain technology.

### Full Reserve vs Fractional Reserve 

Let’s view a blockchain like an Internet Service Provider (ISP) co-op which owns all of the cables in the town 
and has a maximum amount of bandwidth that it can provide at any time. People living in the town can buy shares 
in the ISP and in exchange they are entitled to utilize a portion of the available bandwidth. 

The ISP has two choices, run a “full reserve” or “fractional reserve” system. 
Under a full reserve system each user is only allowed a fraction of the maximum bandwidth proportional to her shares. 
Because not everyone uses the Internet at the same time, the town’s network would be significantly underutilized. 

Under a fractional reserve system the individual users could utilize more bandwidth than they are 
entitled to at any given point in time so long as not everyone uses the Internet at the same time. 
The problem with operating a fractional reserve is that congestion occurs anytime too many people wish
to use the network at the same time. The ISP needs a way to prioritize bandwidth during congested 
periods. In the most extreme case, a fully congested network must revert to a full reserve system. 
The challenge is setting the proper fractional reserve ratio.

## The Solution

The solution is to implement dynamic fractional reserves.  Under this model the blockchain will automatically adjust the reserve ratio for the network during times of congestion. The blockchain will set a target utilization that leaves enough headroom for short term surges in demand. Any time the surges are sustained the blockchain reduces the maximum bandwidth-per-share. When a surge is over and there is surplus capacity the blockchain can slowly increase the bandwidth-per-share.

Bandwidth used by an individual user should be measured over a suitably long period of time to allow that user to time-shift their usage. Users tend to login, do many things at once, then logout. This means that their bandwidth over a short period of time may appear much higher than if viewed over a longer period of time. If the time window is stretched too far then the reserve ratio will not adjust fast enough to respond to short-term surges, if the window is too short then clustering usage will have too big of an impact on normal users.

In our estimate it should be sufficient to measure the average weekly bandwidth usage of users. Every time a user signs a transaction, that transaction is factored into their own individual moving average. Any time a user’s moving average exceeds the current network limit their transaction is delayed until their average falls below the limit.

### Example Implementation

Let B equal a user’s average bandwidth at time T. Let W equal the number of seconds per week, and let N equal the size of the new transaction that occurred S seconds after T. Given this information the blockchain can calculate the new average bandwidth for a user as:


      Bnew = MIN(0,B * (W-S) / W) + N * S / W 

      Tnew = T + S

Each user is entitled to an average weekly bandwidth of:

     Let U = the user’s shares

     Let S = the total number of shares

     Let R = the current reserve ratio between 1 and Rmax

     Let C = the maximum block size capacity 

     Let L = the total blocks per week 

     Let M = C * L * R

    

     Allocation =  M * U / S

A user would be entitled to an average bandwidth of M * U / S. 
Any time a transaction would cause the user's average to go above 
this threshold they would be unable to transact.

The network can then increase the reserve ratio, anytime blocks are less than half the target capacity and decrease it anytime they are more than half. The algorithm used to adjust R can be designed similar to the Bitcoin difficulty adjustment or more advanced algorithms similar to the [Kimoto Gravity Well](http://cryptorials.io/glossary/kimotos-gravity-well/).  

In general the algorithm used should react quickly to decrease the reserve ratio when there is a surge in demand, while acting slowly to reduce the reserve ratio in period of low demand. 

The minimum reserve ratio is 1, and the maximum reserve ratio should be calculated to prevent small stakeholders from consuming all of the available bandwidth. If no one is using the available bandwidth then the reserve ratio can grow until a user with just 1 satoshi of the currency is able to transact every single block.

### Case Study: Bitcoin

To understand how this algorithm would work on Bitcoin it is necessary to estimate a reasonable value for the reserve ratio, R, based on actual usage.  Based upon the total supply of 15 million and a [daily transaction volume of 400K BTC](https://blockchain.info/charts/estimated-transaction-volume?showDataPoints=false&timespan=&show_header=true&daysAverageString=7&scale=0&address=), we can derive a minimum reserve ratio of 38 for Bitcoin. Using the equations we can calculate the weakly bandwidth (in bytes) allowed per BTC to be:

 

    Let C = 1MB = 1024*1024

    Let L  = 1008 (blocks per week)

    Let R = 38

    Let S = 14000000 BTC (supply minus Satoshi’s unmoving coins)

    Let U = 1 BTC 


    C*L*R/S =  2869 bytes per week, or about 5 transactions per week per BTC of balance.


In other words, this simple case study suggests that a user wishing to transact once per week will require about $75 worth of BTC. While this appears to be a lot, this number assumes all users account for an equal amount of the BTC daily volume. The reality is that 400,000 BTC / day does not represent 200,000 users transacting 2 BTC per day. Many individual transactions were greater than 2 BTC. The actual number unique users is known to be less than 500,000 based on the total number of unspent outputs. In other words assuming all unique users transacted once per week that would only require 71,000 users per day and a minimum balance of around $25 worth of BTC. 

All of the above estimates were extremely conservative assuming coins and usage is distributed in a relatively flat manner. The reality is that heavy users, such as exchanges, have a much higher coin-to-usage ratio than lighter users, which in turn means that actual minimum balance requirements are far lower.

#### Impact of Capacity

Blockchain capacity isn’t necessarily capped. It is well within the technological capability of internet infrastructure to increase the Bitcoin block size to 10MB which in turn will reduce the minimum required balance to $2.50.  While Bitcoin currently supports about 3 transactions per second, alternative implementations are capable of over 1000 transactions per second. 
This implies that **accounts holding less than $0.10 could easily transact on average once per week.**    

#### Maximum Number of Unique Users

We can use similar math to calculate the maximum number of unique users that the network can allow to transact once per week as: B*W/T. T represents the average transaction size. This means Bitcoin could support about 2 million users transacting once per week assuming each user had an equal balance.

#### Comparison to Fees

If we assume a user with $25 dollars worth of BTC transacts once per week and pays a $0.04 cent fee each time then they would pay over $2.00 in fees per year. A user would have to earn a 8% rate of return on their $25 dollars just to break even with paying fees. Chances are that users were going to hold their money on the blockchain anyway, so this user with $25 worth of BTC just saved $2 over the course of a year by adopting a rate-limiting approach rather than a fee-based approach. With just $175 they could transact every single day and save $14 per year.

### Account Creation

Rate limiting based upon balances implies that there exist unique accounts with publicly knowable balances. Any account with a balance below the minimum required to transact once per week would be unable to transact. This implies that all new accounts should be funded with at least this minimum balance. It also implies that users wishing to transact in smaller amounts can, so long as they hold a larger balance and reuse the account.  

It is possible for a low-balance account created during a time of low usage to become inaccessible if the network usage picks up. The funds could be recovered at any time by transferring a larger balance into the account.  

In order to maintain a reasonable user experience with a minimum number of hung accounts, all new accounts could start out with a balance 10 times the minimum required to transact weekly. This way even if demand increases by a factor of 10 the account will remain viable.

Any initial account balance would have to come from the user creating the account and not from inflation due to the potential for sybil attacks.

### Justifying Minimum Balances

The concept of forcing users to maintain a minimum balance flows naturally from the 
[value of a user](http://www.forbes.com/sites/tristanlouis/2013/08/31/how-much-is-a-user-worth/#1dadebb692a9). 
Anyone running a business knows that every single user has significant value. Businesses spend anywhere from 
$30 to $200 to acquire a user. Sometimes they pay users directly, other times they pay for advertizing, and 
still other times entire companies are bought just for their user base. After a company acquires a user they 
often given them many *free services* just to keep them around long enough to monetize them through some other means.

[Ripple uses a minimum balance](https://ripple.com/build/reserves/) that scales with account resource use and requires that
new accounts get funded with at least this minimum balance. Currently this minimum balance is about $0.15 which is greater
than the $0.10 we estimated would allow someone to transact freely at least once per week.

A blockchain can enforce a minimum value per user through the simple process of requiring a minimum balance. 
Any business that wishes to bring a new customer to the blockchain can pre-fund that user’s account with the 
minimum balance that would allow them to transact. Requiring a relatively large fee ($1.00) to sign up new 
users will naturally force anyone offering free accounts to vet the quality and uniqueness of each account before
registering them with the blockchain.

Maintaining a minimum balance is effectively the same as making users pay transaction fees with the interest they could have earned on their balance. The minimum balance is simply the balance required to earn enough interest to pay a fee in a short period of time.

Fortunately, the minimum balance required can be as low as a dollar and this is something users can understand and appreciate. The opportunity cost of lost interest doesn’t incur the cognitive cost of a micro-fee and is far more acceptable to users.  

### Adjusting the Reserve Ratio

Rate limiting requires that the network adjust the reserve ratio quickly enough to mitigate the impact of an attacker attempting to flood the network. Let’s assume the attacker has a large balance, say 1% of the available tokens. If we also assume that the network targets 50% utilization, then a sustained attack should find this user throttled to 25% of network capacity assuming everyone else is also using 25% of the capacity. Stated another way, the largest single user should never be able to consume more than 50% of the target capacity unless they own more than 50% of the stake.

Let’s use an initial reserve ratio of 200x. Due to fractional reserves, this means someone holding 1% of the tokens has the right to demand transactions totalling 2x the maximum block size. In order to bring the network usage of the attacker down to 25% the reserve ratio would have to fall to 25x.  This would cause the minimum balance required to transact once per week to grow by 8x.  

The blockchain can establish a response rate that says any sustained increase in usage should be brought down to the target capacity in within a short period of time (say 30 seconds). An attacker attempting to spam the network shouldn’t be able to disrupt service for normal users for more than a minute.

While reductions in the reserve ratio must be quick and non-linear to counter abuse, increases in the reserve ratio should be slow and linear. If the network adjusted in both directions in just 30 seconds then an attacker could pulse the network. A flood of transactions should be corrected in 30 seconds and then take a hour to return to their pre-attack levels. Under this model the attacker could flood the network for 30 seconds per hour or less than 1% of the time.

There must be a slow constant upward pressure on the reserve ratio any time network usage is below 50% until the network hits the maximum reserve ratio. The maximum reserve ratio determines the minimum required stake to flood the network in short bursts.    

Any user with fewer than TOTAL_TOKENS / (2*RESERVE_RATIO) will be unable to produce enough transactions to fill even a single block. With a reserve ratio of 200, this means any user with less than 0.25% of the currency cannot create enough transactions to delay anyone’s service.

### Effectiveness Relative to Fees

To compare the effectiveness of rate limiting to fees we must consider how the two systems react to intentional network flooding by an attacker. Under Bitcoin an attacker with $10,000 dollars could disrupt service for an entire day by filling every single block. The same attacker would be unable to disrupt service for even a single block under the dynamic fractional reserve rate limiting approach. 

If we go to a more extreme case and assume the attacker holds 1% of all coins then we presume an attacker with $60 million dollars. Such an attacker could deny the Bitcoin blockchain service for 16 years unless the miners increased fees or capacity. Even if fees were raised to $15 per transaction, the attacker could still keep the network flooded for 16 days.

Under the rate limiting approach, someone who holds 1% of all coins with an intent to flood the network would achieve their goal for less than 30 seconds. 

### Renting vs Buying vs Timeshares

When someone owns a house they expect the right to use the house for free. If a group of people buy a house together then each can expect the right to use the house proportional to their percentage ownership in the house. A fee based blockchain is like renting the house from its owners, whereas rate limiting is like a timeshare among owners. 

If a house is owned by multiple people then those individuals must decide how they wish to timeshare the house. Someone who owns 50% of the house but only uses it one weekend per year might expect to be paid by the individuals who take their unused time. This is the mindset of a fee based system.

On the other hand, someone who owns 50% of the house is speculating that demand for the house will increase in the future and they will be able to sell their stake for more. Any owner who owns more of a house than they use becomes a real estate speculator. With this mindset rather than collecting rent, they collect appreciation. 

The value of a share is derived from how much time it can potentially grant its owner. Owning 1% of a house and getting it 1 weekend per year is the lowest value of a share. However, if half of the shareholders never use their weekend, then the value per timeshare rises to 2 weekends per year. If those inactive users instead opt to rent their unused time, then it falls back to 1 weekend per year. If those unused timeshares were sold to people who would use them then the value of a timeshare would fall by 50%. Unless the rent collected is greater than the fall in share value the timeshare owners are making an economic miscalculation. 

Using this rationale we can assume that a system based on fees will either be more expensive for its users or be less profitable for its collective owners. An individual small owner may profit by renting out his small time slice, but only at the expense of all other timeshare owners. In effect, the cost of the falling timeshare value is shared among all owners whereas the profits are centralized in the single owner who decided to rent his share.

We can conclude from this that a blockchain is best served by not using usage fees at all. If a usage fee were to be charged as an alternative to rate limiting, then it should be the equivalent of buying enough timeshares and committing to hold them long enough to gain the right use it once. 

Stated another way, a transaction fee should be equal to the minimum account balance necessary to transact once per week and it should be refunded at the end of the week. Assume the minimum account balance is $1 and allows someone to transact once per week. If someone with a $1 balance that wishes to perform 5 transactions at once they will have to increase their balance to $5 for a week either before or after their transactions.  

In theory a market could form where users can borrow the stake required. In practice it is more efficient for users to simply buy and sell the timeshares necessary to meet their desired usage rate. In other words, the cost of negotiating micro-loans is greater than the cost of maintaining a balance suitable for your maximum weekly usage.

### Confidential Transactions
Confidential transactions are used to keep user account balances private. Private balances means that the blockchain doesn’t know the balance of individual accounts and is therefore unable to ration usage. To properly implement rate-limiting the network must know how much capacity a user is authorized to use. Fortunately, this can be implemented without revealing the entire account balance. 

Someone wishing to do a confidential transaction can simply reveal the minimum balance necessary to prove they have held enough shares for a long enough time to authorize the transfer. If they haven’t held the tokens long enough, then the fee can be locked up a week into the future before being returned to the user. 

Under this model all transaction fees can be eliminated while guaranteeing all users a minimum level of service. Most consumers consider locking up a couple of dollars for a week to be “free” even if there is a real opportunity cost. 

If a blockchain wished to avoid locking up funds for a week, then it can set fees based upon an very high interest rate, say 100% APR. Users could then choose between locking up $1 for a week or paying $0.02. Either way the network is guaranteed to win while preventing spam. During heavy usage the minimum fee might raise to $8 for a week or $0.16.  

Ideally users wouldn’t be forced to make this decision because they will have a sufficient balance to permit free transactions without future obligations or fees. Their non-transferrable accrued right to transact makes the perceived cost of a transaction to be 0.  

## Conclusion

Decentralized rate limiting of transactions can enable new types of decentralized applications that were not viable when every use of the application required a micropayment. This new model gives application developers the ability to decide if and when to charge their users for transactions. 


