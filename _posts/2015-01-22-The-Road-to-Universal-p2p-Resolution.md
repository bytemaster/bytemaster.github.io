---
layout: post
title:  "The Road to Universal .p2p Resolution"
author: "indolering"
categories: delegate 
---
The following is a [repost](http://www.indolering.com/universal-p2p-resolution) of the delegate bid by Indolering.  Indolering spent a week with us in early January to help revive our vision for DNS under BitShares.   Indolering has presented one of the best, most comprehensive delegate bids to date.  Here is what he had to say:

<hr/>

I came to BitShares with the express purpose of convincing them to reinvigorate their .p2p efforts.  Thankfully, I was pleasantly surprised to find that the .p2p initiative had fizzled not due to lack of interest but of bandwidth.  The core development team wholeheartedly agreed with my overall plan.  Now I would like to present my roadmap for making .p2p a reality for the BitShares community.


## Introduction

I started contributing to Namecoin because I wanted to build an interoperability solution for .bit so that everyone could visit .bit sites without installing software or altering system settings.  I’ve spent the past couple of years working with my colleagues to systematically break down each one.  From legacy interop to inclusion with the major browsers to domain pricing to interoperating with registrars, I think we’ve architected a solution that will work.

My week at BitShares HQ was to give me time to grok BitShares’s security model, your team, and your community.  BitShares has solved some problems that Namecoin hasn’t, such as pegging assets to USD.  The BitShares’ community is also more open to my proposal for legacy interoperability.  Furthermore, I’m a convert to DPoS:, you can fuel a higher rate of innovation and the security model can accommodate my proposal for legacy interoperability.

However, I want to be upfront in my continued association with Namecoin.  I am a Namecoin contributor who also wants to become a BitShares contributor, but I am in no way being “poached” by BitShares.  Even if delegate pay could sustain me at a market competitive rate, I honestly wouldn’t be of much use without my continued collaboration with my colleagues in the Namecoin community.

Namecoin developers are all volunteers and we are eager to have others tackle this problem. Posts to our internal board regarding potential collaborations and my trip to BitShares HQ have been met with nothing but positive feedback.  The difference between Namecoin and BitShares is similar to that of Debian and RedHat or Firefox and Chrome.

My goal in collaborating with BitShares is to pool our resources and reduce duplication of effort.  Both projects need to work with the IETF, ICANN, certificate authorities DNS providers, and anonymity networks.  It’s time we start working together to end online censorship and make the internet safe from corrupt governments.

# The Long Term Plan

## Legacy Interoperability

Metcalf’s law ensures that .p2p sites must interoperate with the existing web, no website will link to a .p2p site unless all of their visitors can visit the site.  Asking users to install software or changing DNS settings is asking too much!

Initially, we will have to rely on a DNS suffix (i.e. p2p.tld) also known as a pseudo SLD.  However, we must make this solution as secure as traditional TLDs, which requires setting up threshold signing for DNSSEC and electing delegates to sign the zone file.  This task is non-trivial and there are several problems with BitShares original plans for the DNS suffix that I will cover later on.

This solution is not ideal in the long term, if a government shuts down our suffix it shuts down the entire TLD.  However, owning multiple backup .p2p TLDs will turn any attempt at shutting down the TLD into free marketing, the kind that pushes browser and operating system vendors to adopt lightclient resolution directly.

We will also publish signed zone files to Archive.org, so DNS providers can enable .p2p resolution and DNSSEC validating clients won’t have to rely on their DNS providers operational security.  In the medium term, I anticipate pushing .p2p resolution at third party DNS providers (like OpenDNS, Google’s DNS, etc.) as well as universities, major ISPs, and on corporate campuses.

There are several mechanisms (server side, client side, and on the browser level) for detecting support for direct .p2p resolution and forwarding clients from the suffix to the native .p2p domain. Thus, when clients support local resolution, existing DNS suffix links will resolve to the .p2p domain directly.

## Local Lightclient Resolution

I interned at Mozilla and it is a crazy place to work.  The majority of the committers are unpaid and the majority of paid developers are remote, meaning that nearly every developer meeting is broadcast on the internet and that anyone can just drop in on the chat channel.  As a result, the noise floor is VERY high: there a lot of people demanding that Mozilla support various protocols and initiatives.

Take the Metalink project, a standard for listing multiple URLs and transports for a single download.  It has had patch sets for Firefox for years, pending RFCs at the IETF, it is used internally by YUM, supported by cURL, and offered as a distribution method for pretty much every major Linux distro.  It makes downloads faster and more resilient to failure … but Mozilla hasn’t adopted it.

That’s a very long-winded way of saying that we need an overwhelmingly strong case if we ever want adoption by the major browsers and operating systems.  Snowden and the US government’s domain name seizures have made our case much more compelling, but we need still need a few more tricks.

Zooko’s triangle is why I’m here: to make anonymous, censorship-resistant networks usable. Fulfilling this use case is what will enable us, in the long term, to be included in operating systems, browsers, and other network software directly.

Furthermore, China has essentially locked Google and every other Western company out of the world’s largest market.  Indeed, 55% of the worlds population lives in countries that engage in moderate to severe levels of censorship.  It is in these markets that users will be willing to install software add-ons to circumvent censorship and the profit motive to crack these walled gardens will be our vehicle to mass adoption.

# The Plan for 2015

There are a number of problems with .p2p’s existing plans, mostly stemming from a lack of expertise in the relevant areas.  Collectively, it has taken the current Namecoin development team years to develop this expertise.  We also have connections to various communities  (DNS, certificate authorities, the security industry, and standards bodies) that the .p2p team lacks.  Hiring me as a delegate will give BitShares someone to head up this effort that has spent a lot of time reviewing the legal, technical, and usability issues at play.

With your official support, I will include explicit support for BitShares in all of my work and create parallel infrastructure for .p2p.  Let’s get down to what, exactly, that means.

## Funding

I am requesting 2.5 delegates, one at 100% for myself, another at 100% for a security engineer and a third at 10% for operational expenses.  The operational expenses delegate baseline pay rate covers the cost of hiring a system admin to manage the delegates.  The operational expenses delegate’s pay rate will be increased as needed to cover additional expenses such as dedicated servers for the zone signers, .p2p domains, travel costs, and some code bounties for work I do not have time for myself.  All three delegates will be converted into zone signing delegates.

The proposal for 2015 is somewhat optimistic: delegate pay only covers me at ¼ of my industry pay rate (after self-employment taxes).  I am assuming that I will receive grant money to work on Namecoin ¾ time with delegate pay making up the other ¼ time and that the BitShares’ price will not fall dramatically.  If I do not receive grant funding or BitShares’ price falls dramatically, we will need to reevaluate my obligations and pay.

## IETF RFC

The IETF has a draft RFC reserving .onion, .i2p, .bit, and .p2p from use by ICANN.  It is still a draft proposal, but the Tor team has recently expressed that they will begin to push for ratification, and the Namecoin team is going to join them.  I will be spearheading Namecoin’s  efforts here.

Currently, BitShares has no one advocating on their behalf for this draft.  If the BitShares’ community is willing to fund my proposed delegates I will represent both .bit and .p2p at the IETF.  Furthermore, when the RFC was initially introduced, .p2p was being reserved for the original .p2p initiative, not BitShares’.  However, .bit is being reserved for use by the same project that it was initially reserved for.  I do not control these committees so I cannot guarantee anything, but having someone from the .bit project arguing for a rival currency will carry a lot of weight.

Note that reservation through the IETF is the only viable way to reserve .p2p for BitShares.  ICANN’s generic TLD process is prohibitively expensive and forces gTLD applicants to abide by provisions that cannot be supported by a censorship resistant, decentralized TLD (such as a trademark database, a dispute resolution process, etc).

The operational expenses delegate will be used for any travel expenses to attend IETF and ICANN meetings ($3,000-$5,000).

# Legacy Interop

## DNS Suffix

We need several domains to try and prevent attackers from seizing our primary domain. Even with multiple fallbacks, we should try to use the domains most resistant to domain seizures.  I have a list of TLD’s that are cross referenced with the OpenNet Initiative as well as a FOIA request pending with ICE to help determine the safest alternative domains.  I will use this list to generate a list of potential TLDs and then negotiate the purchase of the domains.

Delegate pay will only cover my labor costs; the cost for the additional domains will need to come out from the operational expenses delegate ($1,000 per domain).

DNSSEC
We need to not only sign the DNS suffix but also publish signed zone files so that DNS providers (OpenDNS, Google’s DNS, universities, ISPs, corporate campuses, etc.) can enable .p2p resolution securely.  This is a very complex task.  The first engineering difficulty is that interoperability with DNSSEC means that we must implement a threshold signature scheme that can produce standard RSA public keys with signatures that can be verified by the standard verification routines.  The second is that since we are talking to standard DNSSEC equipment we can’t rely on the normal delegate consensus system.

Thankfully, an academic has published a paper outlining a scheme that produces standard RSA signatures.  There was apparently a Java implementation, but we have been unable to contact the author.  If we cannot get ahold of an existing implementation, we may need to hire a mathematician to help with the reimplementation.

Finally, we must create a system that parallels the traditional TLD zone signing scheme.  The proposed threshold signature scheme’s complexity scales linearly with the number of parties, so it is not feasible to use to scale to a full 101 delegates.  Furthermore, since we cannot easily replace delegates (revoking one delegate requires generating a new ZSK and signing it with the KSK) we need to select a smaller number of very reliable delegates.

The system will require the generation of a Key-Signing-Key (KSK) with 7 trusted parties that store their keys offline.  The KSK will sign a Zone-Signing-Key (ZSK) that is used by delegates to sign the zone files.  We can use a 2Kb ZSK, so there is no need to create and sign a new ZSK every 3 months (.com, .net, etc. use a 1Kb ZSK).  However, to protect against governmental adversaries, the zone signers will need to use dedicated servers and store their keys in hardware security modules.

Delegate pay cover the initial threshold implementation, creating a hardened Linux system, and setting up demonstration zone-signing delegates.  The threshold signature implementation and creating demonstration delegates (including a locked down image and sysop automation) will be covered by the security engineer’s 100% delegate for one year.  The operational delegate will increase its pay rate as needed to cover the demonstrations servers hardware costs (~$2,500).  Sometime in 2016, we will choose the final trusted KSK holders and the additional zone-signing delegates before officially launching .p2p.

## Middleware & Browser Addons

Name records must be converted to a destination format.  For example, a domain might need to be converted for use by Plain-Old-DNS (PODNS), Tor, I2P, etc.  The names and their records must go through validation checks.  Finally, operating systems, browsers, and other applications also need the records served up via DNS; necessitating a standards compliant DNS server.  These tasks fall to a middleware layer that lives outside of the blockchain software.

I am going to fork NMControl (Namecoin’s middleware) convert it to Python 3, replace the RPC library, add record validation, build client libraries in 5+ languages, and add full test coverage.  The resulting product will work with Namecoin’s browser and system level proxy solution and serve for other applications that wish to communicate directly.

I have little experience with Python, I am unfamiliar with the codebase, and I will work on this in parallel to my other responsibilities (like the IETF draft).  Given the level of unknowns, I am going to give myself a wide margin of error and estimate the time for completion of this task to be 6-12 months.

Given that delegate pay is only covering me at ¼ time, this estimate dependent on Namecoin providing additional funding for me through grants or from the community contributing to code bounties. We also need to replace the DNS server with the standards-complaint Unbound server and integrate MITM proxy, which is not my domain of expertise.  These tasks will need to be paid out of the operational expenses delegate ($2,000).

## Internet Freedom Alliance Working Group

There is a need to harmonize standards between BitShares and Namecoin namespace specifications.  There is also potential for collaboration between other groups, such as Tor, I2P, and Freenet.  To facilitate these goals I will create and administer the Internet Freedom Alliance: a working group dedicated to harmonizing standards and increasing collaboration.

The group will largely consist of a mailing list and a Github organization with repositories for formal specifications, unit tests, and reference implementations.  A RFC process for proposing revisions and new standards will be created based on Bitcoin’s BIP workflow and existing standards will receive a formal write up.  The IFA-WG will register as a non-profit legal entity to receive funding from member projects as well as donations.

## .p2p Prelaunch

I’ve worked out a general plan for name reservations, pricing, and other details during my week at BitShares HQ.  However, as the BitShares team can attest, the reasoning for each decision is complex and the full plan will be outlined at a later date.  However, we will create an experimental second-level-domain, x.p2p and progressively enhance it’s capabilities.  This will allow us to test software, such as the middleware and browser add-ons.

I will also work with DNS service providers to build an abstraction layer that will allow registrars to purchase domains using their existing infrastructure.

# Beyond 2015

The majority of the work outlined above should be finished by the end of 2015.  I suspect that over the year, the core development team will be able to switch their focus to features like transaction anonymity, advanced light clients, and setting up the launch of .p2p in early or mid 2016.

It may, at some point, make sense to create a new DAC optimized as a trusted base. There is concern that BTS might not be perceived as “neutral” enough to be a trusted base for core internet infrastructure. It would also make sense to increase the time interval between blocks.  Finally, it may be easier to adopt ZeroCash and other future proposals using a different codebase.  However, in the near term, setting up 101 new delegates, getting adoption in the exchanges, and setting up a competing BitUSD market is just not feasible.

Should it end up being the case that we cannot use the BitShares blockchain, we can always share drop onto BTS for both the share allocation and the initial name ownership. As long as BTS holders benefit from selling the namespace in what eventually becomes a secure decentralized DNS solution, everyone should be satisfied.

It’s impossible to predict the future, and we should evaluate my contributions and potential future as a delegate when 2016 rolls around.  The entire crypto market could tank, or someone could exploit a design flaw so severe that we the couldn’t recover.  Hopefully, I will find external funding, I could be accepted into a Ph.D. program and comfortably work part time for BitShares, or BitShares could explode and I could support myself on delegate pay entirely.

# Conclusion

I’ve laid out a comprehensive plan for both near-term and long-term adoption of .p2p.  I outlined cost estimates for the near-term future and options should the funding situation change.  In the future, it may make more sense to design a currency tailored specifically as a trusted base and share drop on BitShares.  With your support, I believe we can enable universal .p2p resolution thus ending the threat of domain name seizures and making anonymous networks usable.
