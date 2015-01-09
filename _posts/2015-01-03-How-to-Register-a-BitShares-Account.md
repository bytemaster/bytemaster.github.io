---
layout: post
lang: en
title:  "How to Register a BitShares Account"
author: "Daniel Larimer"
categories: 
    - tutorial
---
Many people have been confused about how to create and register their BitShares account. This tutorial will walk you through the process of getting a fully functional registered account on the BitShares blockchain.  

The first step is to download the latest release of BitShares.  At the time of writing BitShares is still in the beta stage of development and updates are made regularlly.  When in doubt you can always find the latest releases on Github

   [https://github.com/BitShares/bitshares/releases](https://github.com/BitShares/bitshares/releases)

After you have downloaded the latest version for your computer and install the BitShares application, start it up and accept the license.   You should then be presented with a screen asking you to set your wallet password.

<center><img src="/media/signup/create_wallet.png"/></center>

This password is used to protect your private keys while they are stored on your computer.  You should make sure you have a reasonably strong password and that your password is not used anywhere else.   This password is not a brain wallet.  Do not assume that if you remember your password that you can recover your funds.  I will walk you through the process of backing up your wallet in a later step. 

The next step is to create an account.  An account is a named public key that allows you to receive funds, [login to websites]({% post_url 2014-12-22-BitShares-Login %})
, and sign messages.   The password you entered in the prior step was to protect your wallet which contains one or more accounts. 

<center><img src="/media/signup/create_account.png"/></center>

After clicking *Create New Account* you will have what is known as an *unregistered account*.  A *unregistered account* is like an unlisted phone number.  No one knows about it unless you share the Account Key with them and they manually add it as a contact. 

<center><img src="/media/signup/account_created.png"/></center>

The next step is to register an account by clicking the blue button to the right of your account name.  This will bring up a dialog that asks you how you would like to pay the transaction fee required to broadcast a transaction to the BitShares network.  

<center><img src="/media/signup/register_account.png"/></center>

Because this is your first account and you have no funds you are given an option for the BitShares faucet to pay your transaction fee on your behalf.   Clicking the blue *Register* button will open your browser to [faucet.bitshares.org](http://faucet.bitshares.org).  
<center><img src="/media/signup/faucet.png"/></center>

Once here you will be asked to login via one of several different services that most people already have an account with.  This is done to prevent abuse only.  Your BitShares account is not publicly tied to the service you choose to login with.

<center><img src="/media/signup/faucet_complete.png"/></center>

After logging in via one of these services your account will be automaticaly and instantly registered on the blockchain.  The faucet gives you an opportunity to share your new account with your friends if you like, but you could simply return to your wallet.

<center><img src="/media/signup/account_registered.png"/></center>

At this point your account page should be updated to reflect that it has been registered.  This means you have successfully created and registered your account with the blockchain and may now use it to receive funds.

## Backup Your Wallet

I recommend backing up your wallet to one or more USB sticks and storing them in a safe location.  As long as you have access to this first backup you should be able to recover any accounts and balances that you have in the future.   Just be sure you don't forget your wallet password from the first step.

To backup your wallet go to the *File* menu and select *Export Wallet*. It will ask you for a location to save your wallet file.  While you only have to do this once to recover your balances, I recomend that you do this periodically to avoid losing your transaction history details which are not all stored on the blockchain. 

<center><img src="/media/signup/ExportWallet.png"/></center>

If you run into any problems following these steps, there are very helpful people on the [BitShares forum](https://bitsharestalk.org) who will be more than willing to help.

