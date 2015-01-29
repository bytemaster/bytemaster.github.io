---
layout: post
title:  "How BitShares Prevents Front Running"
author: "Daniel Larimer"
categories: article 
redirect_from: "/article/2015/1/29/Why-BitShares-Front-Runs-Orders/"
---
Front running happens when a broker executes his own orders prior to executing the orders of his customers.   This can be extremely profitable to the broker which can buy a stock just before a large buy order pushes the price up and then sell the stock just before a large sell order pushes the price down.  This can occur any time one market participant has the ability to see orders from other participants and insert new orders in front of them.   BitShares has an open order book and all transactions are broadcast for all to see with up to 10 seconds notice.  This means that anyone can see your order and change their order to maximize their own profit.  To protect users BitShares uses a *you get what you asked for* (YGWYAF) market engine that produces the same result for the market participants as perfect front running.  This article explains why.

Before going any further about front running, I would like to describe BitShares from different perspective.  Imagine that no one could see the order book except the broker.  The broker's job is to know everyone and what they want.  The traders know that the fastest, most convenient way to get their order matched is to go through the broker rather than attempt to find someone on their own.  So the broker takes requests from everyone and attempts to meet them without telling the traders how he filled their order.  All the clients know is that the broker sold them what they were looking for at the price they agreed to.   The broker makes money by buying low and selling high.   This is in effect what the BitShares blockchain does.  It is the broker that buys the lowest offers and sells to the highest bids while pocketing the change.   There is nothing morally wrong with leveraging your knowledge of market demands and taking actions that enable you to profit.   People do this every day when they notice an arbitrage opportunity.  

# Example of Front Running

When Sam places a large order he looks at the order book and sees that he can get 10 coins for $1, 20 coins for $2, and 20 coins for $3.   Because he wants to buy 50 coins he knows that it will cost him $10 + $40 + $60 or $110 for 50 coins; therefore, he places an order to buy 50 coins with a maximum price of $3 and fund it at $110.   In a traditional exchange the orders execute on a first come, first serve basis so assuming no other orders were placed the order would have been fully filled and Sam would have received 50 coins.  

If the exchange wanted to it could front run Sam's order by executing an order to buy the cheap coins a $1 and $2 and then turn around and sell them back to Sam at $3.  In theory anyone between Sam and the market engine could "front run" him.  This means any peer on the P2P network, his ISP, or his wallet provider. Even Sam's coworkers can front run him if they can observe him filling out his order form. 

On the BitShares block chain orders are grouped into blocks every 10 seconds which means all orders are received “at the same time”.    This means that a bot could see the new order and simultaneously create another order that will cancel offers for $1 and $2 and move them to $3.  Both of these transactions would execute and update the order book before order matching began.   The end result would be that the seller would sell 36.7 coins at $3 each for a profit of 13.3 coins and Sam got less than he expected. 

# Solutions to Front Running 

In our example the average user ended up getting less than they expected and the profits accrued to the advanced user who was able to run a bot or any one that could get their order in first.  Their are many ways people have suggested for solving this, but it all boils down to timing.   Some people suggest “randomizing” the order in which transactions are processed every block.  Others have suggested a two-phase commit and reveal process.   All of these strategies have significant shortcomings.

## Randomizing Orders 

The process of randomizing the order in which orders are processed does not solve the front running process for several reasons.    Assuming all else being equal this will only cut the profitability of front running by 50% (50/50 chance of executing your order first) which means that on average an operator of a bot would still profit 6.65 coins in our example and most importantly half the time Sam would get less than he bargained for.  It also does not solve the problem that block producers can pick and choose which transactions to include which means they can still control the order by delaying confirmation by 1 block.

## Two Phase - Commit and Reveal 

Under the two-phase process orders are initially submitted in an encrypted manner, then after all orders have been placed everyone reveals what they submitted and in theory no one could profit from front running.   This process would reduce, but not eliminate, the profitability of front running if it could be implemented perfectly, but unfortunately that is not possible.   

The issue is the second phase.  A bot can always submit an order and then fail to reveal it after looking at what everyone else revealed.   You cannot add a penalty for failure to reveal because the creator of the reveal transaction has no control over whether or not the block producer will include the transaction in a timely manner.   Therefore, even with a commit and reveal system the block producers can still control order through delays that are blamed on network propagation.    

While the two phase process may reduce the risk, it also greatly harms the user experience.  Orders now take at least twice as long to execute and there is still a large amount of uncertainty over what the outcome will be.  

# Assume Front Running 

If you cannot beat front running, then our best bet is to embrace it.  If every single user places their order with the expectation that it will be front run to their maximal disadvantage then users will naturally change the nature of the orders they place.   Sam was only willing to pay an average of $2.20 per coin so he would place a single order for 50 coins at $2.20 and could not be taken advantage of by the bot because he either gets $2.20 per coin or he gets nothing. A bot that saw Sam’s order would be wise to cancel its order at $1 and $2 and move it all to $2.20 because that would maximize the amount received by the bot without harming any other market participants.    It would only hurt the profits of the exchange which would have made $16 dollars had the bot not changed the orders.

If Sam was a bargain hunter and willing to take his time, then he could still get all 50 coins for $110 assuming there was no one else competing with him to buy coins.  First he would place an order for 10 coins at $1.  After that was filled he would place an order for 20 coins at $2 and lastly he would place an order for 20 coins at $3.    This process took 3 times longer than placing a single “market order” with a $3 limit, but it protected Sam while preventing the bot from making any money what-so-ever by being faster than a human.  

At the end of the day those looking to get the best prices for large orders will simply use wallet-side market orders rather than rely on the block chain to do it for you.   This will result in more transactions and thus more transaction fees, but at just a few cents per transaction it will easily be made up by the savings of more efficient order matching.   

# Conclusion

The BitShares order matching engine must operate on a *you get what you asked for* and nothing more basis or someone else will profit by giving you what you asked for and nothing more.   This approach gives the user maximal control and allows wallets to automate walking the order book one price level at a time.  

## Better than a Centralized Exchange

In many ways this is far superior to the approach used by centralized exchanges because the user never has to trust the exchange not to front run them.   All centralized exchanges keep their order submissions secret from the users which means they can easily front run without detection.   The problem is so bad with centralized exchanges that regulators had to pass a law against front running which Wall Street has effectively side-stepped with high frequency trading.   If you need to make a “law” then perhaps that is a sign that the system is flawed and a new system should be adopted.    

BitShares makes no apologies for not having a traditional order matching algorithm at the block chain level.  Every exchange should use our approach and move the order-book-walking algorithm to the clients computer where everyone is more or less equal. 


