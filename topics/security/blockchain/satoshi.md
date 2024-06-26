# Satoshi Nakamoto's posts

<br>![miscellaneous image](https://raw.githubusercontent.com/AnselmoGPP/Learn_Computer_Science/master/resources/miscellany.jpg)


## Table of Contents

+ [**References**](#references)
+ [**metzdowd.com cryptography mailing list**](#metzdowd.com-cryptography-mailing-list)
+ [**P2P foundation**](#p2p-foundation)


## References

- [**metzdowd archive](https://www.metzdowd.com/pipermail/cryptography/2008-October/date.html)
- [P2P foundation](http://p2pfoundation.ning.com/profile/SatoshiNakamoto)


## metzdowd.com cryptography mailing list

### Satoshi Nakamoto (Fri Oct 31 14:10:00 EDT 2008)

I've been working on a new electronic cash system that's fully peer-to-peer, with no trusted third party.

The paper is available at: [http://www.bitcoin.org/bitcoin.pdf](http://www.bitcoin.org/bitcoin.pdf)

The main properties:

- Double-spending is prevented with a peer-to-peer network.
- No mint or other trusted parties.
- Participants can be anonymous.
- New coins are made from Hashcash style proof-of-work.
- The proof-of-work for new coin generation also powers the network to prevent double-spending.

Bitcoin: A Peer-to-Peer Electronic Cash System

Abstract.  A purely peer-to-peer version of electronic cash would allow online payments to be sent directly from one party to another without the burdens of going through a financial institution. Digital signatures provide part of the solution, but the main benefits are lost if a trusted party is still required to prevent double-spending.  We propose a solution to the double-spending problem using a peer-to-peer network.  The network timestamps transactions by hashing them into an ongoing chain of hash-based proof-of-work, forming a record that cannot be changed without redoing the proof-of-work.  The longest chain not only serves as proof of the sequence of events witnessed, but proof that it came from the largest pool of CPU power.  As long as honest nodes control the most CPU power on the network, they can generate the longest chain and outpace any attackers.  The network itself requires minimal structure.  Messages are broadcasted on a best effort basis, and nodes can leave and rejoin the network at will, accepting the longest proof-of-work chain as proof of what happened while they were gone.

Full paper at: [http://www.bitcoin.org/bitcoin.pdf](http://www.bitcoin.org/bitcoin.pdf)

Satoshi Nakamoto

### James A. Donald (Sun Nov 2 18:46:23 EST 2008)

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

### 




























## P2P foundation
