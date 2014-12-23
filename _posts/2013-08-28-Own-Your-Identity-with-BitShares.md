---
layout: post
lang: en
title:  "Own Your Identity with BitShares"
author: "Daniel Larimer"
featured: true
categories: 
    - article
---
Who *really* owns your online identity?  I can assure you that any ownership you perceive is an illusion and ultimately your online identity is not currently under your control.  Chances are your identity is tied to your e-mail address and every service you sign up for uses email verification as the primary means of identification.   If you ever lose access to your email account then you have lost access to many of your other accounts as well.   Even worse, if someone is able to read your emails then they can reset your passwords on every service you use and effectively steal your ‘identity’ and take your money with it.     Ultimately Google, Apple, Yahoo and others own your online identity and as much as you may trust any individual company, these companies can be strong-armed by governments you may not trust.   But even if you have complete faith in these companies and the government, the security offered under this model is so poor that every single day accounts are compromised in mass. 

It is problems like these that the BitShares community has set its sights on solving.  Inspired by the protocols behind Bitcoin, we are developing technologies that will help you take control over your identity, finances, and communication while eliminating most any form of identity theft.

There is a common belief that security and ease of use are at always at odds.   Encryption has been available to the average computer user since the early 1990’s with the release of Blowfish, PGP, and other open encryption systems and the underlying algorithms have been well-known since before the Internet.    Despite the technical know-how, truly secure systems have not become widespread.  This is widely because they are so difficult to use that the cost of security has far exceeded the perceived benefits even when high security is almost a necessity.

I come from a very computer-literate family and have attempted to set up secure email communication with those closest to me.   Despite sending instructions, YouTube videos, and screen sharing sessions it was almost impossible to get working reliably.  The situation has been so bad that even Edward Snowden was unable to get Glenn Greenwald to setup PGP encryption in a timely manner so they could securely communicate.

Most people end up giving every company they deal with the keys to their identity by using the same password everywhere.

With experiences like these it is no wonder why almost no one uses secure e-mail and everyone relies on ‘passwords’ to access even their most important information such as their bank accounts.    Passwords are considered the most user-friendly security that is easy enough for the average individual to use.   Unfortunately, to be secure your password must be long and generally hard to remember.  Your password becomes your identity because knowing it allows anyone to access your accounts and to impersonate you online.   To complicate matters, users must choose between the ease of use of a single password for every service and the greater security of having a unique, long, hard-to-remember password with every service they use.   Most people end up giving every company they deal with the keys to their identity by using the same password everywhere.    Once again, ease of use trumps security.

It is clear that the problem with security is not in the realm of encryption, but in making it easy to use.   This is where BitShares has combined the technologies of Bitcoin, BitMessage, Namecoin, with several new methods to  bring the benefits of encryption to the masses.  Apple introduced the Macintosh in 1984 with the promise of showing us why 1984 won’t be like ‘1984’.  This message has remained close to our heart; we intend to fulfill the promise Apple made thirty years ago.

The primary challenge with making cryptography easy to use lies in the secure exchange of what is known as a ‘public key’.    A public key is nothing more than a very large random number that is paired with another large random number known as a private key.   Assuming you can exchange public keys with everyone you know and keep your private key secret then the rest of the problem is easy in comparison.

As the famous 1999 paper [“Why Johnny Can’t Encrypt”](http://www.gaudior.net/alma/johnny.pdf) demonstrates, users have a very hard time keeping this information straight.  There is a steep learning curve to understand the ‘theory’ behind it and the information is ultimately just ‘random data’ so it is a black box.   Unfortunately, exchanging the information is only part of the problem, the other part is validating the information provided.    If someone provides you Johnny’s public key in an email, how can you trust it?

The traditional solution is to use centralized Certificate Authorities that handle the complex task of verifying that the ‘owner’ of an email really does control the private key.  Unfortunately, this solution has once again removed your control over your identity and given both the Certificate Authority (CA) and your e-mail provider control over your online identity.    You can be sure that the NSA can forge signatures from a CA.   Even without worrying about the NSA, the CA system is only as secure as the least secure company you implicitly trust.

### Introducing BitShares ID  (aka BitID) 

   The BitShares ID system eliminates the need for a Certificate Authority and replaces it with a new kind of block-chain which is secured by proof-of-work in a manner similar to Bitcoin.   When you download the BitShares client and start it up for the first time, it will join the BitShares network and start synchronizing with the global name-chain by downloading it to your local computer.  You would then select a user name of your choice and the client would check to make sure it is not in use.  After selecting your name, your client will starting doing the proof-of-work required to enter your name in the name-chain with everyone else.    Like Bitcoin, this process takes some time to both mine and be confirmed by other peers on the network.   Within a reasonable period of time your computer will have finished reserving your name and having it confirmed by the network.

   From this point you are ready to start texting, emailing, and trading with your friends.  To send a friend a message all you need to do is know their BitShares ID user name.  This information is easily exchanged over the phone or other traditional communication channels and readily understood by everyone.   Enter their name in the ‘to field’, type your message, and click send.

   As you can see, communicating within the BitShares ecosystem will be even easier than traditional email.  There is no company to sign-up with, no certificate authority to pay, and no mail server configuration to manage.   Despite being even easier to use than traditional unencrypted email, it is also several orders of magnitude more secure than even the most carefully setup and configured secure mail system available today.

   There are several reasons why BitShares communication is more secure than anything on the market.   The first reason is that 100% of the message is encrypted, including the sender and receiver.  No one is able to collect the meta data on your e-mails and use that information to discover your social network.   Second, there are no trusted third parties such as e-mail providers or Certificate Authorities with the power to compromise your account and impersonate you.   Third, it is so easy to use that it will be much harder for users to accidentally compromise their security.

### Integrated Wallet 

   In addition to putting you in control of your identity and communication, BitShares will put you in control of your money by making Bitcoin and other crypto-currencies as easy to use as Paypal while being more secure than even Bitcoin is today.    This is made possible by using the BitShares ID system and communication system to automatically and securely negotiate payment address with everyone on your contact list.   Users of the BitShares Wallet interface will never have to see a Bitcoin address again because sending money to someone is literally as easy as sending them an e-mail.  Select a contact, enter an amount, click send.

   A significant factor in the difficulty of using Bitcoin in commerce is that you must adopt a foreign pricing system and deal with very volatile prices.   This makes it difficult to  interpret prices and make purchasing decisions. BitShares solves this ease-of-use challenge through by creating BitAssets such as BitUSD, BitEUR or BitGold.   Users will be able to use a crypto-currency denominated in a familiar unit and spend it more securely, privately, and quickly than any other system on the market.    This will make crypto-currencies so easy to use and familiar that ease of use will no longer be a limiting factor to adoption.

###  Owning Your Identity

   With BitShares ID and the surrounding ecosystem it will become feasible for you and Johnny to finally take control of your online identity.   With relatively straightforward integration, companies can enable you to use your BitShares ID to provide ‘single-sign-on’ for the entire internet.   You will no longer have to trust any business to protect your personal information and most businesses will no longer even need to collect it.   The result is that identity theft and the resulting financial, credit, and reputation theft will become much less common and no longer within reach of every scammer with a phishing site.

