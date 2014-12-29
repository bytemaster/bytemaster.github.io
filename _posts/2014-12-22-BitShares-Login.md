---
layout: post
title:  "BitShares Login"
author: "Daniel Larimer & Nathan Hourt"
categories: article

sharing: true
featured: true
banner_image: "/media/cover_asset.jpg"
---
In a previous article I ask the question ["Who *really* owns your online identity?"]({% post_url 2013-08-28-Own-Your-Identity-with-BitShares %}).  Under todays internet the answer is simple: Not You.   Your online identity is managed by your login credentials which are usually tied to your email account.  Google, Apple, Microsoft, Yahoo and/or your ISP collectively control the vast majority of email accounts and therefore own your online identity.  At any time they can freeze your account or recover the password for every other service you use from Facebook to your online banking.   Imagine how many things you would lose access to if you were locked out of your email account!

### Too Many Passwords 

It seems like almost every website these days has some kind of use account.  Every online store, bank, forum, and blog wants you to create an account with a new username and password.   Many individuals leave a site as soon as it requires them to register an account.  To "help" solve this problem many websites have adopted technologies such as [Open ID](http://openid.net/get-an-openid/what-is-openid/) or [OAuth](http://oauth.net/).   You have probably experienced these systems when you are asked to "Login with Facebook" or "Login with Google".   This system is great at eliminating the need to have multiple accounts and manage multiple passwords, but it has a side effect of making a single account "all powerful".   Everyone from Reddit, to Github, to Twitter and Linked In is offering 3rd party sites the ability to use their login system as the "one system" because they want to own your identity.    

### Introducing BitShares Login

BitShares Login provides a decentralized alternative to Open ID and OAuth that allows you to retain complete control over your online identity while maintaining your privacy.   When you use Facebook to log into a blog so you can post a comment you are dependant upon Facebook to *let you* login and you reveal to Facebook that your account is linked to a 3rd party service.   When you use BitShares Login there are no 3rd party middle men to snoop or interfere.

Every BitShares user has a registered account that they use for everything from messaging to sending money and trading.  This registered account has reserved a globally unique user name tied to a revocable public key. BitShares Login automates a simple handshake that allows you to prove to a website that you are the owner of the registered account.     

BitShares Login provides a secure and easy-to-use login procedure, allowing users to create and access accounts on websites without creating a password. Furthermore, the login system is designed to be simple to implement, allowing websites to quickly and easily add BitShares Login support to their existing platforms.

BitShares supports logging in to websites using an identity on the blockchain. This login is implemented as a two-way mutual authentication handshake, where the server first authenticates itself to the client, and then the client authenticates itself to the server. At the end of the login, the client has a web browser open with an authenticated session with the server, the server has a username and public key for the client, and the server and browser both hold a 512-bit shared key which may be safely used for symmetric encryption of messages between the client and server. The handshake is performed without revealing either the client's public key or the shared key to an eavesdropper, which facilitates private and confidential browsing. All of this is done without trusting a central authority which could be compromised or leveraged.

The login protocol is implemented using BitShares URLs. This allows a fluid user experience, in which the user can securely authenticate to the website with her BitShares wallet instead of a password, and the server need not store any passwords or implement its own authentication system.

### User Demo

If you would like to experience BitShares login in a real world application, you can try our [Simple Machines Forum plugin](https://github.com/BitShares/Bitshares-SMF-Login) at the [BitSharesNation test forum](http://bitsharesnation.org).  When a user clicks the "Login with BitShares" button it will start the login process.

<center>
<img src="/media/SimpleMachineLogin.png"/>
</center>

If it is the first time a user has used BitShares login they may be presented with a dialog asking the user for permission to launch BitShares.  The dialog looks something like this:

<center>
<img src="/media/ExternalProtocolRequest.png"/>
</center>

If you grant permission then BitShares will launch and ask you to unlock you wallet and then present you with the following dialog:

<center>
<img src="/media/LoginDialog.png"/>
</center>

In this particular case, my wallet has an account named "angel" and the website has identified itself as "testingtoday".  If I click "OK" then I will be directed back to my web browser and will be fully logged into the website as "angel".   As you can see the process is very similar to using Facebook to log into a 3rd party site (such as [BTC38](https://en.btc38.com)).  The difference is that instead of directing you to another website, it directs you to a local application installed on your computer. 

### Future Improvements 

While redirecting to a local application is the most secure approach, it isn't always the most convenient.  We are actively working on creating a fully hosted wallet similar to [Blockchain.info](https://blockchain.info).  With a fully hosted wallet the server stores your private key encrypted by a password and allows you to access your account with your password from any browser.  This is still an improvement over Facebook login because a hosted wallet can keep all private keys client side which means the wallet provider never has access to your key (assuming they can be trusted).  At any time you can move your private keys from a hosted wallet to a local wallet and take your identity with you.

### Conclusion

BitShares Login provides a real alternative to Open ID and has the power to make cryptographic logins easy to use.  Eventually the login protocol can be adapted to provide extra information about your identity (such as a shipping address) or Know Your Customer compliance.  Taking back control over your identity is the first step toward individual freedom.  

### Developer Demo

Below this point this article dives into more technical details regarding how BitShares Login works.  

A PHP script which demonstrates the BitShares Login protocol is available [here](https://github.com/BitShares/qt_wallet/blob/master/login.php).

### The Protocol

The BitShares Login protocol involves four steps:

1. The server creates a Login URL containing the server's authentication tokens and the URL of the page the server uses to authenticate users, and embeds it in a web page viewed by the user
2. The user opens the URL, which triggers the BitShares client to verify the server's tokens and ask the user if they wish to log in with the authenticated server
3. The BitShares client opens a new browser window to the page the server specified in the Login URL, with the client's authentication tokens in the query string
4.  The server receives the page request, verifies and expires the tokens, and starts an authenticated session with the client

Only steps 1 and 3 involve network communications, making the protocol a fast and simple two-way handshake. After completing step 4, the server holds the client's public key on BitShares (which was not leaked to an eavesdropper), and both the browser and server hold a shared secret. We now examine each of these four steps in detail.

#### Step One

The server calls wallet_login_start on a local BitShares RPC server, which generates a one-time key pair and returns a Login URL of the following format: bts:Login/SO/SO'/ SO is the server's one-time public key, and SO' is a signature of SO generated with the server's private BitShares account key, Sa. The server appends its domain and login page path to the URL, and embeds it in a page to be viewed by the client. The final URL in the page is formatted as: bts:Login/SO/SO'/www.example.com/login.php

#### Step Two

When the user opens the Login URL, it is passed to her local BitShares wallet for processing. The wallet parses out SO and SO', and uses these two to derive SA, the server's public account key. The wallet looks up this key on the blockchain and retrieves the server's registered account name. If the server has not registered its account key on the blockchain, the URL is invalid and the login fails.

The wallet prompts the user asking them if they wish to log in, showing them the server's verified account name on the blockchain.

#### Step Three

If the user directs the wallet to complete the login, the wallet generates its own one-time key pair, and combines its private one-time key Co with SO to derive S, a 512-bit shared secret. The wallet signs S with its private account key Ca to yield signature S', then opens a new browser window to www.example.com/login.php?client_key=CO&client_name=alice&server_key=SO&signed_secret=S'#S where CO is the client's public one-time key. Note that S is placed in the URL fragment, so the browser does not send it over the network, but it can be read by javascript executing in the browser. The client_name parameter is provided in case the user has not registered her name on the blockchain.

#### Step Four

The server receives the page request, and calls wallet_login_finish on its BitShares RPC server, passing SO, CO, and S' as arguments. The server's wallet uses SO to look up So, the corresponding one-time private key, and then combines So with CO to derive S. It then combines S with S' to derive the client's public account key, CA, and returns S and CA to the server.

The server now holds CA, the client's public account key, has a username for the client, and shares secret key S with the client.

IMPORTANT: Like all data coming from a client, the username is not verified, and should not be trusted implicitly. It may belong to another account on the blockchain, or it may not be registered at all. The account which holds the public key which logged in may be registered with a different name. The name which comes on the query string should be viewed as a request from the client to be called by that name, but it has no guarantee of uniqueness, authenticity or validity.

### The Math

Like the rest of the cryptography used in blockchain technology, the BitShares Login protocol is implemented using the Elliptic Curve Digital Signature Algorithm (ECDSA), with Elliptic Curve Diffie Hellman (ECDH) for symmetric key exchange.

Detailed analysis of these schemes is outside the scope of this document; however, there are some important properties provided by these schemes which are used in the Login protocol as well as TITAN and other components of the larger BitShares protocol.

The first property is the ECDH key exchange, which is used to generate shared secret S above. Recall that the client and server each generated a one-time key pair, with (So,SO) for the server and (Co,CO) for the client. ECDH uses the fact that So*CO = Co*SO = (Sx,Sy). The x-coordinate, Sx of the resulting point, is used as the shared secret S.

The other property it is important to highlight is a unique characteristic of the ECDSA signature verification algorithm. In most asymmetric cryptosystems, a function V(K, S, T) takes the public key, signature, and signed text as parameters and returns a simple true/false value indicating whether the signature is valid or not. This is the behavior of RSA, for example. In ECDSA, however, a verification function takes only two parameters, S and T, and returns K. The signature is valid if the returned K matches the signer's public key. This is a significant difference, as both the client and server in the above Login protocol use signatures to recover the other party's public key, which they then look up on the blockchain to determine the other party's identity. In other words, the signature verification is not used to determine if the signature is valid, but to determine the identity of the other party.

### The Security

We are not aware of any practical attacks on the Login protocol. We assume that a malicious third party may eavesdrop and/or tamper with any data sent over the internet, namely the Login URL containing SO and SO', as well as the client's response (CO,SO,S'). Only public, one-time keys are sent over the internet, thus the identity of the client is protected because only a holder of So, the server's private one-time key, can calculate S in order to recover CA, the client's public account key. The server's identity is regarded as public, and any eavesdropper could easily verify SO and SO' to derive SA.

A malicious party may attempt to impersonate the server by replacing SO and SO' in the Login URL; however, if the malicious party uses his own private key to generate signature SO', his identity will be revealed when the corresponding public key is used to look up his account on the blockchain. If he uses an unregistered private key to generate SO', the corresponding public key will not be found on the blockchain, and the user's wallet will detect the tampering and refuse to complete the Login procedure.

The attacker may also replay a valid SO and SO' from a previously eavesdropped session, but this would simply cause the client to construct a different S which would still be unknown to the attacker, and furthermore, the server would reject the login attempt as the SO returned in the client's response would be expired. If the attacker switched out the SO in the client's response with the original value sent by the server, the server would regard the login attempt as valid, but would derive a different S than the client, and the signature verification on S and S' would fail, alerting the server to the tampering.

A malicious party may attempt to hijack the client's session by replacing CO and S' in the client's response, but this will be of no value to the attacker as they would either be registering a new account with the server with an unrecognized key, or they would be logging into their own account. Only if the attacker held Ca would he be able to cause the server to derive CA, even if the attacker knows CA himself. The attacker could leverage this as a denial of service attack, by repeatedly tampering with the client's authentication tokens causing the login to fail, but if the attacker has control over the communication channel, he already has the ability to denial of service simply by dropping all messages.

Thus, given the semantic security of ECDSA and ECDH, the worst attack a malicious party with full control over the communication medium could leverage is denial of service.

### Development Status

Both the [Simple Machines Forum Plugin](https://github.com/BitShares/Bitshares-SMF-Login) and the [BitShares Wallet](https://github.com/BitShares/bitshares/releases) are under active development.  There are known bugs with the entire process that we hope to clean up in the months ahead.   If you have questions and would like help integrating BitShares Login with your own service you should check out [this thread](https://bitsharestalk.org/index.php?topic=12119.msg159953#msg159953) at [bitsharestalk.org](https://bitsharestalk.org).  Once all the bugs are worked out BitShares Talk will be one of the first of many production services to use BitShares Login.

