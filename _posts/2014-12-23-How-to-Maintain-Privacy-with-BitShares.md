---
layout: post
lang: en
title:  "How to Maintain Privacy with BitShares"
author: "Daniel Larimer"
categories: 
    - article
---
Privacy is a funny thing.  It is difficult to gain, easy to loose, and impossible to restore.   I have spent a good deal of time looking for solutions to maintain my privacy and one such resource was J.J. Luna’s book “<a href="http://www.amazon.com/gp/product/1250010454/ref=as_li_tl?ie=UTF8&camp=1789&creative=9325&creativeASIN=1250010454&linkCode=as2&tag=bytesblog-20&linkId=SSHOFCVMCA4DAUAP">How to Be Invisible</a><img src="http://ir-na.amazon-adsystem.com/e/ir?t=bytesblog-20&l=as2&o=1&a=1250010454" width="1" height="1" border="0" alt="" style="border:none !important; margin:0px !important;" />”.   In his book he outlines the great lengths some people must resort to when they have stalkers following them.  One point that he drives home again and again is that you should never actually live at an address that anyone knows.  

<iframe style="width:120px;height:240px;float:left;margin-right:20px" marginwidth="0" marginheight="0" scrolling="no" frameborder="0" src="//ws-na.amazon-adsystem.com/widgets/q?ServiceVersion=20070822&OneJS=1&Operation=GetAdHtml&MarketPlace=US&source=ac&ref=tf_til&ad_type=product_link&tracking_id=bytesblog-20&marketplace=amazon&region=US&placement=1250010454&asins=1250010454&linkId=PD72VD6BU5KVSCKV&show_border=true&link_opens_in_new_window=true">
</iframe>

In one of his examples a man and wife had just moved to a new home which had been purchased using the privacy protecting strategies in his book.  Then there was a medical emergency and his wife wasn’t thinking and gave their home address and name to 911 so the ambulance could find the house.    This one brief lapse forced them to sell their home and start over.

This is an example of the nature of privacy.  A single mistake can undo years of planning and cost you more than you would like to recover from.  

### Privacy with Bitcoin

Since Bitcoin launched its supporters have have pitched it as a solution for financial privacy.  The theory is that “no one knows your (Bitcoin) address” and as long as that is true you can have privacy.    Unfortunately, every time you make a transaction you reveal at least one of your addresses to the other party of the transaction.  The normal advice is to give each person in your life a different address for sending you funds.   This allows Alice and Bob to send you money without either of them knowing how much the other sent.   
After some time passes you decide to sell all of your bitcoins so you send them to Bitstamp.  Under the hood Bitcoin will generate a single transaction that combines the addresses you gave Alice and Bob and pays the funds to an address given to you by Bitstamp.    Your privacy has just been compromised.  Alice now knows how much Bob paid you and Bob knows what Alice paid you and in all likelihood Bitstamp knows everything.   

If you want to keep your privacy you have to send Bitstamp your funds in two transactions and ask Bitstamp to provide you with two new addresses.  You should probably spread the transfers out over several days.  When you make a transfer to someone you have to never tie two of your addresses together.    This may be possible if you never have any change, but that rarely happens.    The result is that despite your best efforts there is a high degree of information leakage with each and every transaction.    Your change addresses become toxic temptations because as soon as you use a change address as part of another transaction you have just linked the two transactions.   Each new transaction leaves a toxic hook for the next transaction.    

Your only hope is to send all of your incoming funds from Alice, Bob, and your change address to a laundry service.   A laundry service receives a lot of payments to a common address from many different people and then (after a time delay) sends your funds back to a clean address. This would protect your privacy against almost everyone but the laundry service itself.  Using a laundry service to remove the privacy compromising stench from your coins means trusting a 3rd party service which is a money transmitter under the law and thus required to perform Know your Customer verification or risk violating anti-money-laundering (AML) laws.   This service will end up being grey market and could disappear with your coins at any moment.  

The reality is that privacy isn’t entirely within your control.  If you are the only person on the network who is attempting to use best practices for protecting privacy, then, by process of elimination, your balance is revealed to all.    Privacy is the art of hiding in the crowd and becomes increasingly difficult the smaller the crowd becomes.  

### Privacy with BitShares 

BitShares has a transaction ledger similar to Bitcoin.  This means that your privacy can be compromised in the same way.  With TITAN (Transfer Invisibly to Any Name) we have provided one layer of protection: generating a unique address for every transfer.  Unlike Bitcoin, BitShares uses named accounts which makes it easier to remember and share your account name.   TITAN only keeps your transaction history private, with no link to your account name, to 3rd parties.   The parties to the transaction know the balance address and account name are linked.   

Like Bitcoin, Alice and Bob can discover how much money I have when I decide to combine my balances to make a payment to an exchange, in this case BTC38.   Now BTC38 knows my account name and which balances it was linked to.  

If you stop to consider the fact that most crypto currency transactions are only a few “hops” from an exchange and that exchanges know who almost everyone is then through the process of elimination an exchange, and therefore the government, can unmask most balances with a high degree of certainty.  

### Voting Compromises Privacy 

BitShares can also leak your privacy if you attempt to vote for delegates.  Chances are the slate of delegates you support is unique in some way from most other people.   This reduces the size of the crowd you are attempting to hide in, potentially to just you.   Your voting preference becomes like a secondary address that can tie all of your transactions together.

You end up having to make a choice:
  
1. Don’t vote for anyone (reducing network security)
2. Vote the same way as a large number of people (joining a party) 
3. Vote for a random subset with every transaction (compromise in security vs privacy)
4. Give up on Privacy 

The BitShares wallet has some support for these various options, though it is far from easy to use or understand at this point in time.   

### Privacy always comes with a Price 

It would be nice if we could make privacy the default option.  If everyone was using best practices for privacy then we would all be better off.   The problem is that privacy isn’t free and it comes with a price.    It takes time, effort, patience, and consistency.    You cannot be lazy and expect to keep privacy.    

Software can only help automate the process to some extent.  It can auto schedule payments and track dirty coins.   It can automate sending your funds to a mixing service and it can even recombine multiple partial payments into a single logical payment.   

Software cannot protect you against the people you transact with.  It cannot protect you against a corrupt mixing service.   It cannot eliminate the delays or fees associated with mixing your funds.

There are some advanced software techniques that would enable a mixing service to operate without even the service knowing what funds went to whom.   These software services use things like e-cash or zerocoin.   But these software techniques come with a price as well, every one participating has to do so in fixed denominations. 

At the end of the day most people conclude the price is too high.  They cannot keep up with all the details required at all times and thus give up.     

### What anyone can know about your balance.

Software algorithms can analyze the block chain and automatically group balances and transactions together.   It can create a probabilistic model that can tell everyone about how many unique users there are and about how much money they have.  For every balance in the ledger you can derive a meaningful probability about whether or not it belongs to the same individual.   So if someone learns one of your balances because they did business with you, then they can likely guess about how much money you have unless you are pro active about mixing your funds.  The more points of contact someone has on the network the more they can infer.  A merchant or payment processor has much more information than a passive observer or individual user.  

### Piratical Steps to Protect your Privacy 

While the privacy offered by block chain technology isn’t perfect, it is good enough for most people who are not trying to hide from large exchanges, merchants, or the government.  If all you want to do is keep your financial information relatively private from your neighbors then that can be easily achieved.

#### 1. Register your Account with a Faucet 

When you register you account name with the block chain it ties one of your balances to that account name.   If you register all of your accounts with the same balance then all of your account names will be linked together by the balance that paid the transaction fee.  You also need to be careful if you update an account because that operation will require a transaction fee that will come from one of your balances.  

#### 2. Maintain Multiple Accounts 
 
The BitShares wallet allows you to maintain multiple named accounts.  The funds in each account are kept entirely separate and the wallet will not link transactions together.   I recommend one account for trading, one for checking, and one for savings.  Be careful when you transfer funds between accounts because that will only result in one degree of separation.

#### 3. Vote a well known Slate, or Don’t Vote. 

Be careful when you vote.  All accounts in the same wallet vote the same way.   If you are going to vote then you should vote for a common slate that has been published by a trusted individual and which many other people are also using.  In a future article I will provide more information about how to control your voting.  When in doubt, don't vote.   

### Does Privacy Really Matter?

Today people use Bitcoin and value it at $4 billion dollars despite having little if any real privacy built in.   Ripple uses one key for your entire balance and almost every Ripple account is connected to a Gateway that practices Know Your Customer accounting.   Everyone on the Ripple network who does business with you can discover your balance.   The only coin that attempts to build in mixing services is Dark coin and it is worth less than $10 million at the time of this writing.  

The vast majority of people using crypto currencies have such a small amount in play that a compromise in privacy doesn’t effect them much.   In many ways the size of your house, the make of your car, the brand of phone, and speed of your computer reveal far more about your net worth than anything leaked on the block chain.  

For those who care about privacy they will probably manage their funds through a trusted 3rd party for both legal and security reasons.  The truly paranoid will utilize the most advanced mixers and double check every interaction with the outside world.   These people are in the minority to such an extent that they can almost be ignored.    After all, what good is all of that privacy if you cannot easily convert it to tangible wealth without giving up your privacy?

### Ease of Use Wins

The market has spoken and most people choose ease of use over privacy.  This means that even BitShares with its TITAN transactions is more difficult to use than transparent transactions.  Transparent transactions make implementing light weight wallets and observable off line wallets much easier.  TITAN requires you to have your wallet unlocked to receive funds, which is a security concern for e-commerce applications.   We have designed technical solutions that make TITAN easier, but these technical solutions have their limits and quirks.     

Given the success that Ripple has had with their entirely transparent solution and the traction that Bitcoin has gathered with its relatively weak and manual process I cannot help but conclude that we should prioritize ease of use over privacy.  

In my opinion, all future wallets should make TITAN opt-in.  You will still send to a name, but it will not generate a one-time key for the transaction.    With this in place then block explorers such as bitsharesblocks.com would be able to monitor your balance for you.  Web wallets and light weight wallets would follow very quickly.   The speed of development in the BitShares ecosystem would accelerate.

Lets make BitShares super simple and reliable, then we can talk about adding complexity required to maintain privacy.
