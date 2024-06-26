# Satoshi Nakamoto's posts

<br>![miscellaneous image](https://raw.githubusercontent.com/AnselmoGPP/Learn_Computer_Science/master/resources/miscellany.jpg)


## Table of Contents

+ [**References**](#references)
+ [**metzdowd.com cryptography mailing list**](#metzdowd.com-cryptography-mailing-list)
+ [**P2P foundation**](#p2p-foundation)


## References

- [**metzdowd archive**](https://www.metzdowd.com/pipermail/cryptography/2008-October/date.html)
- [**P2P foundation**](http://p2pfoundation.ning.com/profile/SatoshiNakamoto)


## metzdowd.com cryptography mailing list

#### Satoshi Nakamoto (Fri Oct 31 14:10:00 EDT 2008)

I've been working on a new electronic cash system that's fully peer-to-peer, with no trusted third party.

The paper is available at: 

[http://www.bitcoin.org/bitcoin.pdf](http://www.bitcoin.org/bitcoin.pdf)

The main properties:

- Double-spending is prevented with a peer-to-peer network.
- No mint or other trusted parties.
- Participants can be anonymous.
- New coins are made from Hashcash style proof-of-work.
- The proof-of-work for new coin generation also powers the network to prevent double-spending.

Bitcoin: A Peer-to-Peer Electronic Cash System

Abstract.  A purely peer-to-peer version of electronic cash would allow online payments to be sent directly from one party to another without the burdens of going through a financial institution. Digital signatures provide part of the solution, but the main benefits are lost if a trusted party is still required to prevent double-spending.  We propose a solution to the double-spending problem using a peer-to-peer network.  The network timestamps transactions by hashing them into an ongoing chain of hash-based proof-of-work, forming a record that cannot be changed without redoing the proof-of-work.  The longest chain not only serves as proof of the sequence of events witnessed, but proof that it came from the largest pool of CPU power.  As long as honest nodes control the most CPU power on the network, they can generate the longest chain and outpace any attackers.  The network itself requires minimal structure.  Messages are broadcasted on a best effort basis, and nodes can leave and rejoin the network at will, accepting the longest proof-of-work chain as proof of what happened while they were gone.

Full paper at: 

[http://www.bitcoin.org/bitcoin.pdf](http://www.bitcoin.org/bitcoin.pdf)

Satoshi Nakamoto

#### James A. Donald (Sun Nov 2 18:46:23 EST 2008)

> I've been working on a new electronic cash system that's fully peer-to-peer, with no trusted third party.
> 
> The paper is available at: [http://www.bitcoin.org/bitcoin.pdf](http://www.bitcoin.org/bitcoin.pdf)

We very, very much need such a system, but the way I understand your proposal, it does not seem to scale to the required size.

For transferable proof of work tokens to have value, they must have monetary value.  To have monetary value, they must be transferred within a very large network - for example a file trading network akin to bittorrent.

To detect and reject a double spending event in a timely manner, one must have most past transactions of the coins in the transaction, which,  naively implemented, requires each peer to have most past transactions, or most past transactions that occurred recently. If hundreds of millions of people are doing transactions, that is a lot of bandwidth - each must know all, or a substantial part thereof.

### Satoshi Nakamoto (Sun Nov 2 20:37:43 EST 2008)

>We very, very much need such a system, but the way I understand your proposal, it does not seem to scale to the required size.
>
>For transferable proof of work tokens to have value, they must have monetary value.  To have monetary value, they must be transferred within a very large network - for example a file trading network akin to bittorrent.
>
>To detect and reject a double spending event in a timely manner, one must have most past transactions of the coins in the transaction, which, naively implemented, requires each peer to have most past transactions, or most past transactions that occurred recently. If hundreds of millions of people are doing transactions, that is a lot of bandwidth - each must know all, or a substantial part thereof.

Long before the network gets anywhere near as large as that, it would be safe for users to use Simplified Payment Verification (section 8) to check for double spending, which only requires having the chain of block headers, or about 12KB per day.  Only people trying to create new coins would need to run network nodes.  At first, most users would run network nodes, but as the network grows beyond a certain point, it would be left more and more to specialists with server farms of specialized hardware.  A server farm would only need to have one node on the network and the rest of the LAN connects with that one node.

The bandwidth might not be as prohibitive as you think.  A typical transaction would be about 400 bytes (ECC is nicely compact).  Each transaction has to be broadcast twice, so lets say 1KB per transaction.  Visa processed 37 billion transactions in FY2008, or an average of 100 million transactions per day.  That many transactions would take 100GB of bandwidth, or the size of 12 DVD or 2 HD quality movies, or about $18 worth of bandwidth at current prices.

If the network were to get that big, it would take several years, and by then, sending 2 HD movies over the Internet would probably not seem like a big deal. 

Satoshi Nakamoto

### John Levine (Mon Nov 3 08:32:39 EST 2008)

> As long as honest nodes control the most CPU power on the network, they can generate the longest chain and outpace any attackers.

But they don't. Bad guys routinely control zombie farms of 100,000 machines or more. People I know who run a blacklist of spam sending zombies tell me they often see a million new zombies a day.

This is the same reason that hashcash can't work on today's Internet -- the good guys have vastly less computational firepower than the bad guys.

I also have my doubts about other issues, but this one is the killer.

R's,
John

### Satoshi Nakamoto (Mon Nov 3 11:23:49 EST 2008)

>But they don't.  Bad guys routinely control zombie farms of 100,000 machines or more.  People I know who run a blacklist of spam sending zombies tell me they often see a million new zombies a day.
>
>This is the same reason that hashcash can't work on today's Internet -- the good guys have vastly less computational firepower than the bad guys.

Thanks for bringing up that point.

I didn't really make that statement as strong as I could have.  The requirement is that the good guys collectively have more CPU power than any single attacker. 

There would be many smaller zombie farms that are not big enough to overpower the network, and they could still make money by generating bitcoins.  The smaller farms are then the "honest nodes".  (I need a better term than "honest")  The more smaller farms resort to generating bitcoins, the higher the bar gets to overpower the network, making larger farms also too small to overpower it so that they may as well generate bitcoins too.  According to the "long tail" theory, the small, medium and merely large farms put together should add up to a lot more than the biggest zombie farm.

Even if a bad guy does overpower the network, it's not like he's instantly rich.  All he can accomplish is to take back money he himself spent, like bouncing a check.  To exploit it, he would have to buy something from a merchant, wait till it ships, then overpower the network and try to take his money back.  I don't think he could make as much money trying to pull a carding scheme like that as he could by generating bitcoins.  With a zombie farm that big, he could generate more bitcoins than everyone else combined.

The Bitcoin network might actually reduce spam by diverting zombie farms to generating bitcoins instead.

Satoshi Nakamoto

### James A. Donald jamesd@echeque.com (Mon Nov 3 15:20:13 EST 2008)

Satoshi Nakamoto:
> Long before the network gets anywhere near as large as that, it would be Safe for users to use Simplified Payment Verification (section 8) to check for double spending, which only requires having the chain of block headers,

If I understand Simplified Payment Verification correctly:

New coin issuers need to store all coins and all recent coin transfers.

There are many new coin issuers, as many as want to be issuers, but far more coin users.

Ordinary entities merely transfer coins.  To see if a coin transfer is OK, they report it to one or more new coin issuers and see if the new coin issuer accepts it. New coin issuers check transfers of old coins so that their new coins have valid form, and they report the outcome of this check so that people will report their transfers to the new coin issuer.

If someone double spends a coin, and one expenditure is reported to one new coin issuer, and the other simultaneously reported to another new coin issuer, then both issuers to swifly agree on a unique sequence order of payments.  This, however, is a non trivial problem of a massively distributed massive database, a notoriously tricky problem, for which there are at present no peer to peer solutions.  Obiously it is a solvable problem, people solve it all the time, but not an easy problem. People fail to solve it rather more frequently.

But let us suppose that the coin issue network is dominated by a small number of issuers as seems likely.

If a small number of entities are issuing new coins, this is more resistant to state attack that with a single issuer, but the government regularly attacks financial networks, with the financial collapse ensuing from the most recent attack still under way as I write this.

Government sponsored enterprises enter the business, in due course bad behavior is made mandatory, and the evil financial network is bigger than the honest financial network, with the result that even though everyone knows what is happening, people continue to use the paper issued by the evil financial network, because of network effects - the big, main issuers, are the issuers you use if you want to do business.

Then knowledgeable people complain that the evil financial network is heading for disaster, that the government sponsored enterprises are about to cause a "collapse of the total financial system", as Wallison and Alan Greenspan complained in 2005, the government debates shrinking the evil government sponsored enterprises, as with "S. 190 [109th]: Federal Housing Enterprise Regulatory Reform Act of 2005" but they find easy money too seductive, and S. 190 goes down in flames before a horde of political activists chanting that easy money is sound, and opposing it is racist, nazi, ignorant, and generally hateful, the recent S. 190 debate on limiting portfolios (bond issue supporting dud mortgages) by government sponsored enterprises being a perfect reprise of the debates on limiting the issue of new assignats in the 1790s.

The big and easy government attacks on money target a single central money issuer, as with the first of the modern political attacks, the French Assignat of 1792, but in the late nineteenth century political attacks on financial networks began, as for example the Federal reserve act of 1913, the goal always being to wind up the network into a single too big to fail entity, and they have been getting progressively bigger, more serious, and more disastrous, as with the most recent one.  Each attack is hugely successful, and after the cataclysm that the attack causes the attackers are hailed as saviors of the poor, the oppressed, and the nation generally, and the blame for the the bad consequences is dumped elsewhere, usually on Jews, greedy bankers, speculators, etc, because such attacks are difficult for ordinary people understand.  I have trouble understanding your proposal - ordinary users will be easily bamboozled by a government sponsored security update.  Further, when the crisis hits, to disagree with the line, to doubt that the regulators are right, and the problem is the evil speculators, becomes political suicide, as it did in America in 2007, sometimes physical suicide, as in Weimar Germany.

Still, it is better, and more resistant to attack by government sponsored enterprises, than anything I have seen so far.

> Visa processed 37 billion transactions in FY2008, or > an average of 100 million transactions per day. That many transactions would take 100GB of bandwidth, or the size of 12 DVD or 2 HD quality movies, or about $18 worth of bandwidth at current prices.

> If the network were to get that big, it would take several years, and by then, sending 2 HD movies over the Internet would probably not seem like a big deal. If there were a hundred or a thousand money issuers by the time the government attacks, the kind of government attacks on financial networks that we have recently seen might well be more difficult.

But I think we need to concern ourselves with minimizing the data and bandwidth required by money issuers - for small coins, the protocol seems wasteful.  It would be nice to have the full protocol for big coins, and some shortcut for small coins wherein people trust account based money for small amounts till they get wrapped up into big coins.

The smaller the data storage and bandwidth required for money issuers, the more resistant the system is the kind of government attacks on financial networks that we have recently seen.

### Ray Dillinger bear@sonic.net (Thu Nov 6 00:14:37 EST 2008)

James A. Donald:
> If I understand Simplified Payment Verification correctly:
> 
> New coin issuers need to store all coins and all recent coin transfers.
> 
> There are many new coin issuers, as many as want to be issuers, but far more coin users.
> 
> Ordinary entities merely transfer coins.  To see if a coin transfer is OK, they report it to one or more new coin issuers and see if the new coin issuer accepts it. New coin issuers check transfers of old coins so that their new coins have valid form, and they report the outcome of this check so that people will report their transfers to the new coin issuer.

I think the real issue with this system is the market for bitcoins.  

Computing proofs-of-work have no intrinsic value.  We can have a limited supply curve (although the "currency" is inflationary at about 35% as that's how much faster computers get annually) but there is no demand curve that intersects it at a positive price point.

I know the same (lack of intrinsic value) can be said of fiat currencies, but an artificial demand for fiat currencies is created by (among other things) taxation and legal-tender laws.  Also, even a fiat currency can be an inflation hedge against another fiat currency's higher rate of inflation.   But in the case of bitcoins the inflation rate of 35% is almost guaranteed by the technology, there are no supporting mechanisms for taxation, and no legal-tender laws.  People will not hold assets in this highly-inflationary currency if they can help it.  

Bear

### Satoshi Nakamoto satoshi@vistomail.com (Thu Nov 6 15:15:40 EST 2008)

>[Lengthy exposition of vulnerability of a systm to use-of-force monopolies ellided.]
>
>You will not find a solution to political problems in cryptography.

Yes, but we can win a major battle in the arms race and gain a new territory of freedom for several years.

Governments are good at cutting off the heads of a centrally controlled networks like Napster, but pure P2P networks like Gnutella and Tor seem to be holding their own.  

Satoshi

### Perry E. Metzger perry@piermont.com (Fri Nov 7 12:32:23 EST 2008)

List Moderator's Edict of the Day:

A bunch of people seem anxious to branch the discussion of cryptographic cash protocols off into a discussion of the politics of money. I'm a rabid libertarian myself, but this isn't the rabid libertarian mailing list. Please stick to discussing either the protocols themselves or their direct practicality, and not the perils of fiat money, taxation, your aunt Mildred's gold coin collection, etc.

Perry

### zooko zooko@zooko.com (Fri Nov 7 16:10:31 EST 2008)

Hey folks: you are welcome to discuss money politics over at the p2p-hackers mailing list:

[http://lists.zooko.com/mailman/listinfo/p2p-hackers](http://lists.zooko.com/mailman/listinfo/p2p-hackers)

I'm extremely interested in the subject myself, having taken part in two notable failed attempts to deploy Chaumian digital cash and currently being involved in a project that might lead to a third attempt.

Regards,

Zooko
---
[http://allmydata.org](http://allmydata.org) -- Tahoe, the Least-Authority Filesystem
[http://allmydata.com](http://allmydata.com) -- back up all your files for $10/month


### Hal Finney hal@finney.org (Fri Nov 7 18:40:12 EST 2008)

Bitcoin seems to be a very promising idea. I like the idea of basing security on the assumption that the CPU power of honest participants outweighs that of the attacker. It is a very modern notion that exploits the power of the long tail. When Wikipedia started I never thought it would work, but it has proven to be a great success for some of the same reasons.

I also do think that there is potential value in a form of unforgeable token whose production rate is predictable and can't be influenced by corrupt parties. This would be more analogous to gold than to fiat currencies. Nick Szabo wrote many years ago about what he called "bit gold"[1] and this could be an implementation of that concept. There have also been proposals for building light-weight anonymous payment schemes on top of heavy-weight non-anonymous systems, so Bitcoin could be leveraged to allow for anonymity even beyond the mechanisms discussed in the paper.

Unfortunately I am having trouble fully understanding the system. The paper describes key concepts and some data structures, but does not clearly specify the various rules and verifications that the participants in the system would have to follow.

In particular I don't understand exactly what verifications P2P nodes perform when they receive new blocks from other nodes, and how they handle transactions that have been broadcast to them. For example, it is mentioned that if a broadcast transaction does not reach all nodes, it is OK, as it will get into the block chain before long. How does this happen - what if the node that creates the "next" block (the first node to find the hashcash collision) did not hear about the transaction, and then a few more blocks get added also by nodes that did not hear about that transaction? Do all the nodes that did hear it keep that transaction around, hoping to incorporate it into a block once they get lucky enough to be the one which finds the next collision?

Or for example, what if a node is keeping two or more chains around as it waits to see which grows fastest, and a block comes in for chain A which would include a double-spend of a coin that is in chain B? Is that checked for or not? (This might happen if someone double-spent and two different sets of nodes heard about the two different transactions with the same coin.)

This kind of data management, and the rules for handling all the packets that are flowing around is largely missing from the paper.
 
I also don't understand exactly how double-spending, or cancelling transactions, is accomplished by a superior attacker who is able to muster more computing power than all the honest participants. I see that he can create new blocks and add them to create the longest chain, but how can he erase or add old transactions in the chain? As the attacker sends out his new blocks, aren't there consistency checks which honest nodes can perform, to make sure that nothing got erased? More explanation of this attack would be helpful, in order to judge the gains to an attacker from this, versus simply using his computing power to mint new coins honestly.

As far as the spending transactions, what checks does the recipient of a coin have to perform? Does she need to go back through the coin's entire history of transfers, and make sure that every transaction on the list is indeed linked into the "timestamp" block chain? Or can she just do the latest one? Do the timestamp nodes check transactions, making sure that the previous transaction on a coin is in the chain, thereby enforcing the rule that all transactions in the chain represent valid coins?

Sorry about all the questions, but as I said this does seem to be a very promising and original idea, and I am looking forward to seeing how the concept is further developed. It would be helpful to see a more process oriented description of the idea, with concrete details of the data structures for the various objects (coins, blocks, transactions), the data which is included in messages, and algorithmic descriptions of the procedures for handling the various events which would occur in this system. You mentioned that you are working on an implementation, but I think a more formal, text description of the system would be a helpful next step.

Hal Finney

[1] [http://unenumerated.blogspot.com/2005/12/bit-gold.html](http://unenumerated.blogspot.com/2005/12/bit-gold.html)

























## P2P foundation
