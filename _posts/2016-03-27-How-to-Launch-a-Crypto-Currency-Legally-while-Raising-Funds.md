---
layout: post
title:  "How to Launch a Crypto Currency Legally while Raising Funds
"
author: "Daniel Larimer"
categories: article

---

Thousands of startups are entering the cryptocurrency space and attempting to determine how their business model meshes with the numerous edicts handed down to us by unelected bureaucrats at numerous government agencies such as the IRS, FinCEN, and the SEC to list three agencies just in the United States.

The rules are changing faster than anyone can figure them out. There are 100’s of crypto currency projects out there and few have been fined. A notable exception is Ripple Labs which was fined $700,000 for selling its XRP token without following KYC/AML regulations handed down by FinCEN. XRP was the #2 crypto currency for years until recently displaced by Ethereum.  

I have been attempting to interpret all of these edicts so that I can help others avoid regulatory land mines all around us. One of those land mines is giving legal advice without being a lawyer, so **what follows is just my opinion and should not be construed as legal advice**. Please consult with your own lawyers and draw your own conclusions.

## The Regulations 

Lets review some of the most important regulations facing businesses in the crypto currency space. There is one major question that needs to be answered: “Does my business need to register as a Money Services Business (MSB) or a Money Transmitter?”. If the answer is “Yes” then your journey into the rabbit hole of regulations is just beginning. If the answer is “No”, then chances are  you are simply a *user of virtual currency* in which case no regulations apply to you that I am aware of.

Here are the relevant documents from FinCEN:
 
- March 18, 2013 [FIN-2013-GOO1 - Regulations to Persons Administering, Exchanging, or Using Virtual Currencies](https://www.fincen.gov/statutes_regs/guidance/html/FIN-2013-G001.html) 
- October 27, 2014  [FIN-2014-R012 - Regulations to a Virtual Currency Payment System](https://www.fincen.gov/news_room/rp/rulings/pdf/FIN-2014-R012.pdf)
- August 14, 2015 - [FIN-2015-R001 - Issuing Negotiable Certificates on Blockchain](https://www.fincen.gov/news_room/rp/rulings/pdf/FIN-2015-R001.pdf)


>  A user who obtains **convertible virtual currency** and uses it to purchase real or virtual goods or services is not an MSB under FinCEN's regulations. Such activity, in and of itself, does not fit within the definition of "money transmission services" and therefore is not subject to FinCEN's registration, reporting, and recordkeeping regulations for MSBs.

When it comes to the law, definitions are everything. In this case the definition of **convertible virtual currency** is critical.

> This guidance addresses "convertible" virtual currency. This type of virtual currency either has an equivalent value in real currency, or acts as a substitute for real currency.


## Are you an Administrator of a Convertible Virtual Currency?

FinCEN outlines three categories of virtual currency, the first two being relatively traditional business models like [e-gold](https://en.wikipedia.org/wiki/E-gold). If your business holds assets on behalf of others and enables customers to transfer or trade those assets to or with other customers then your business is regulated. It doesn’t matter whether the asset is Gold, Silver, Bitcoin, or Toilet Paper.  Additionally issuing redeemable notes or deposits might be considered a security by the SEC.  

What is interesting is that Bitcoin (BTC) and Ripple (XRP) are considered “convertible virtual currencies” too.

>   A final type of **convertible virtual currency** activity involves a de-centralized convertible virtual currency (1) that has no central repository and no single administrator, and (2) that persons may obtain by their own computing or manufacturing effort.

FinCEN says the following activity is safe and free from MSB regulations:

> A person that creates units of this convertible virtual currency and uses it to purchase real or virtual goods and services is a user of the convertible virtual currency and not subject to regulation as a money transmitter. 

On the other hand, they say the following is unsafe and requires compliance with MSB regulations.

> By contrast, a person that creates units of convertible virtual currency and sells those units to another person for real currency or its equivalent is engaged in transmission to another location and is a money transmitter. In addition, a person is an exchanger and a money transmitter if the person accepts such de-centralized convertible virtual currency from one person and transmits it to another person as part of the acceptance and transfer of currency, funds, or other value that substitutes for currency.

This guidance is surprisingly consistent with their other rules if you view Bitcoin as property similar to gold or silver (like the IRS does).  The confusing bit about this regulation is what constitutes *creating* and *selling*?  

An [official letter from FinCEN in December 2013](http://www.coindesk.com/fincen-bitcoin-miners-need-not-register-money-transmitters/) clarified that miners who mine “for themselves” do not have to register as a MSB.  

>  "In undertaking such a conversion transaction, the user is not acting as an exchanger, notwithstanding the fact that the user is accepting a real currency or another convertible virtual currency and transmitting Bitcoin, so long as the user is undertaking the transaction solely for the user’s own purposes and not as a business service performed for the benefit of another. A user’s conversion of Bitcoin into a real currency or another convertible virtual currency, therefore, does not in and of itself make the user a money transmitter.”

### What if you create a currency without mining it?
This is what Ripple Labs did with their XRP token. They created 100% of the currency and proceeded to give it away to attract users. Here is the [FinCEN findings on Ripple](https://www.fincen.gov/news_room/nr/pdf/Ripple_Facts.pdf).  

 > The currency of the Ripple network, known as “XRP,” was **pre-mined**. In other
words, unlike some other virtual currencies, XRP was fully generated prior to its
distribution. 

> The Guidance also defines an administrator of virtual currency as a person
or entity “engaged as a business in issuing (putting into circulation) a virtual
currency, and who has the authority to redeem (to withdraw from circulation) such
virtual currency.” 

> Both exchangers and administrators are MSBs that must register with FinCEN unless
they fall within an exemption.

> From at least March 6, 2013, through April 29, 2013, Ripple Labs **sold convertible
virtual currency known as “XRP.”**

If you create a currency without mining, also known as pre-mining, and then sell this currency for fiat money or substitute (aka convertible virtual currency like Bitcoin), then you could be considered a MSB and subject to all of the rules and regulations that apply. 

# How to Launch a Crypto Currency Legally

The strategy I present below attempts to error on the conservative side on how to launch a crypto currency without becoming an administrator or money transmitter or exchanger. In other words, it may be possible to violate my rules while still complying with the law in certain circumstances. 

Here is the readers digest version:

- Do not pre-allocate any currency to yourself or others.
- Do not sell currency directly to others
- Aways sell through a regulated exchange.
- Complete the currency and protocol prior to launch.
- Never promise to do anything for the currency 

## Raising Capital 

The challenge faced by startups is that they need capital and the most efficient means of raising capital is to sell tokens. The question is how do you get tokens to sell if you cannot pre-allocate any currency to yourself. The other question is what constitutes legal **computing or manufacturing effort** as authorized by FinCEN as being legal *use of convertible virtual currencies*?

In my opinion the following guidelines represent a way to stay within the unregulated realm of *user of a convertible virtual currency*.

- Allocate 100% of the currency via a computer algorithm that does not specify any specific public keys to receive funds. Once tokens have been distributed, the token creation the algorithm may use internal metric such as coin-days, voting, etc to create and distribute additional tokens. 
- Publicly announce your token and release your source code prior to creating the first token. There is little difference between pre-allocation and mining without the potential for competition. 
- Spend thousands of dollars mining your own currency *after a public launch*.  
- Sell your mined currency through a regulated exchange.

Mining a token can be cheaper than issuing shares in a C-class corporation in the State of Delaware.  The taxes for issuing just 200,000 shares in a company amount to thousands of dollars per year. On the other hand, you can mine 200,000 tokens for under $500 **if there is little competition**.

## Bitcoin Community “Cultural Regulations”

The Bitcoin community has adopted its own informal cultural regulations around how a new crypto currency should be launched. The biggest conventions include:

- No Premine - allocating tokens prior to launch 
- No Instamine - heavily bias issuance toward early miners
- No IPO/ICO - selling tokens prior to launch
- Only mine a small amount for yourself
- Open Source MIT / BSD license

On top of these rules, there are many other expectations:

- Significant advanced notice
- Binaries for all platforms 
- Lots of Documentation 

A startup that attempts to comply with all of the FinCEN regulations *AND* all of the Bitcoin community *cultural regulations* finds itself in a pickle. If you reveal enough information about your product with enough warning then the market will speculatively place a high value on your tokens. The higher the value the market places on the tokens, the more capital is wasted on a computational competition to acquire the tokens. 

If the goal is to raise money legally then a startup must maximize the capital gain it realizes between the time it mines the tokens and the time it sells them on an exchange.  If a high initial value is placed on the token, then the potential for capital gains is much lower and therefore the potential to legally raise money through the sale of your token falls dramatically.

On the other hand, if you comply with FinCEN and ignore the cultural expectations then your token will start out life a pariah and have low initial value.  If you completely open source your software then clones can pop up to compete against you.  

Perhaps the Bitcoin Communities cultural regulations are a blessing in disguise. By intentionally violating every one of their expectations you can minimize your token’s value at launch while still legally mining a token for minimal cost. 

Those in the Bitcoin community who are forward-thinking enough to recognize the value of alternative allocation strategies can mine these pariah coins and profit along with their creators.

The government has handed us a huge blessing by officially recognizing computational effort and manufacturing of coins as a legal, unregulated, means of introducing a convertible virtual currency to the market. If the Bitcoin community were wise, it would embrace this blessing and welcome with open arms every project.  However, if the community did change its opinion, then all of a sudden mining completion for tokens currently being shunned would increase dramatically. Such a change could end up closing the regulatory loophole by making it cheaper to comply with regulations than to compete with opportunistic miners.  

## Conclusion

There are no easy answers in this space and everything could change in an instant with a fresh interpretation 
of the rules by our unelected bureaucratic overlords. For the time being, it is my opinion that it is possible 
to create a new crypto-platform while staying within the realm of a *user* and out of the realms *administrator*, 
*issuer*, and *transmitter*. You just need thick skin and the ability to ignore the Bitcoin 
[pharisees](https://en.wikipedia.org/wiki/Pharisees) and the angry mob they incite to nail you to a cross for 
failing to sacrifice your creation to the prevailing mining gods.

