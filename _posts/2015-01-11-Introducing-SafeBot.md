---
layout: post
title:  "Introducing BitShares SafeBot"
author: "Daniel Larimer"
categories: article 
---
When it comes to crypto currencies there are no take-backs.  A single mistake could send thousands of dollars to the wrong person never to be seen again.  Crypto currencies go to great lengths to minimize human error.  This normally takes the form of a checksum tacked on to the end of the payment address.    With Bitcoin this checksum doesn’t impact the user experience in any significant way because all addresses are essentially a random string of characters that no sane human would ever attempt to type by hand.    In BitShares we have attempted to make the whole user experience easier and replace random addresses with human friendly names, but in the process introduced a new point of failure: typos.   To reduce the risk of typos we have implemented a new feature that we call your SafeBot.

Every account is associated with a unique randomly generated robot that is derived from your account name.  If someone types even a single character wrong the robot will look completely different.  Once you become familiar with your SafeBot and the SafeBots of your friends and businesses you will have a high degree of confidence that you are sending to the proper account.   

## Examples

<table>
<tr>
<td> <img src="http://robohash.org/bytemaster.png"/> </td>
<td> <img src="http://robohash.org/dan.png"/> </td>
<td> <img src="http://robohash.org/bitshares.png"/> </td>
</tr>
<tr>
<td align="center"> bytemaster </td>
<td align="center"> dan </td>
<td align="center"> bitshares </td>
</tr>
</table>

SafeBot is just our term for what is known as a visual hash or visual checksum.  In our case we have opted to use the service provided by [robohash.org](http://robohash.org) which is fully open source.   

## Is this better than a checksum?

I am a sophisticated Bitcoin user and I get paranoid every time I request or make payment in Bitcoin.  One time I gave someone the wrong address and 3 BTC went to some lucky soul out there.   Other times I might mix up addresses that other people have given me.   The only reliable way to send to the right address is to manually maintain an address book.  Once you do this it is back to the potential for human error if you happen to select the wrong contact.

Bitcoin addresses create a huge hurdle for new users and mobile payments.  QR codes have become the preferred way to exchange a Bitcoin address and that is very cumbersome compared to entering an account name.   Bitcoin addresses are so obtuse that the checksum almost never plays a role because all addresses are moved around via copy and paste rather than manual input.

Our eyes play tricks on us when looking at strings of characters.  Take the following string: MMVWMVNMNMMN.  Can you reliably read and recognize it at a glance?   Even if you have an address with a proper checksum, can you be sure it is the proper address?    Checksums are useful for ensuring the address is internally consistent, but it does not help you verify that it is the right address for your intended recipient. 

To be fair, using a 3 digit checksum combined with a human readable name will provide better security than a random name with a checksum.  We will be adding an option for a manual double check on the checksum in addition to the SafeBot.   

## Verbal Communication 

Human readable and pronounceable account names have a huge advantage if you are trying to share secure contact information over the phone, TV, or radio.  It is much easier to communicate a 3 digit checksum and a human pronounceable name than a large random string.   While you may not want to send a large payment to someone this way, you can easily use it to send a secure message or a small tip.  

With registered account names and SafeBot, it becomes possible to communicate payment instructions verbally where as it was impossible using Bitcoin addresses. 

## Written Communication 

Have you ever wanted to share your bitcoin address with someone when you were away from your computer and wallet?    Using registered names and a description of the robot or a 3 digit check code you can easily remember and clearly write down your account.  This makes it easy to exchange payment information with anyone at any time even if you don’t have a phone handy.  

## How you should use your SafeBot

To get the most mileage out of your SafeBot you should make sure it is visibly associated with your online identities.   You should have it displayed on your business website, your Facebook page, and your blog.   It should be the image for your github account.  The more places you use your SafeBot in association with your real world identity the more familiar people will become with it and the less likely they will make a mistake when transferring to you.   

At the very least you should always display your SafeBot when you are asking for payment from the user.  This way they can visually compare the SafeBot shown in the wallet with the one displayed on your website.  A visual match gives people much greater confidence when making a payment and reduces the likelihood of messy mistakes. 

## Nothing is Perfect 

If you do not stop and think before every transaction it is entirely possible that you could miss the fact that the SafeBot isn't the same.   Of course, it is even more likely you will miss a change in a checksum.  

<iframe style="margin:0px" width="640" height="375" src="//www.youtube.com/embed/Ng4heqMAbCA" frameborder="0" allowfullscreen></iframe>

The lesson of this video is to always stop and double check everything.   

## Using SafeBot with Bitcoin 

Soon [bitsharesblocks.com](http://bitsharesblocks.com) will provide an API that will allow bitcoin wallets to lookup the bitcoin address that corresponds to a BitShares account.   This will allow users to communicate a Bitcoin address with all the ease of BitShares.  And that is just another way that BitShares will contribute to the massive growth of the Bitcoin ecosystem.   





 


