# Blockchain

<br>![miscellaneous image](https://raw.githubusercontent.com/AnselmoGPP/Learn_Computer_Science/master/resources/miscellany.jpg)

## Table of Contents

+ [**References**](#references)
+ [**Bitcoin**](#bitcoin)
  + [History of money](#history-of-money)
  + [Bitcoin introduction](#bitcoin-introduction)
  + [Cryptography](#cryptography)
+ [**Ethereum and smart contracts**](#ethereum-and-smart-contracts)
+ [**Web3**](#web3)
+ [**DeFi**](#defi)
+ [**Privacy coins**](#privacy-coins)


## References:

- Harsh Strongman (2022) *Teach yourself crypto*. Retrieved from [teachyourselfcrypto.com](https://teachyourselfcrypto.com/).

- **Bitcoin**
  - [History and evolution of money](https://lifemathmoney.com/the-history-and-evolution-of-money/)
  - [How does BTC actually work?](https://www.youtube.com/watch?v=bBC-nXj3Ng4)
  - [Bitcoin - Cryptographic hash function](https://www.youtube.com/watch?v=0WiTaBI82Mc)
  - [How secure is 256 bit security?](https://www.youtube.com/watch?v=S9JGmA5_unY)
  - [Public key cryptography](https://www.youtube.com/watch?v=GSIDS_lvRv4)
  - [What are digital signatures?](https://www.youtube.com/watch?v=s22eJ1eVLTU)
  - [The GNU privacy handbook](https://gnupg.org/gph/en/manual.pdf)
- **Ethereum and smart contracts**
- **Web3**
- **DeFi**
- **Privacy coins**


## Bitcoin


### History of money

Humans are not self-sufficient, nor can exist in isolation. We need things other humans provide, and we provide things other humans need. We do **exchanges** (you give something you have in order to get what you want). Eventually, we invented agriculture and domesticated animals, so we were able to settle down at one place and created a society. Our labor became specialized (farmers, doctors, fishermen...), which increased productivity and quality of goods produced. 

**Barter system**: Until a few thousand years ago, human's exchange system was the barter system (we exchange goods and services with each other directly). The exchange ratio was determined based on demand and supply. However, it had limitations: no common measure of value (each good was pegged to different sets of other goods: 1 wheat bag = 2 fish or 5 haircuts or 4 pots...), need of double coincidence of wants (both parties need what the other provides), indivisibility of certain goods (if my goat is worth 10 pots, I cannot get 5 pots), lack of standards for deferred payments (credit transactions involve disputes about the quality and value of goods used), and storage problems (storing wealth is complicated: stored fishes will spoil).

**Commodity money**: These issues can be solved by using a widely consumed commodity that's always in demand and can be exchange for other goods. Romans used salt (divisible, non-perishable, limited, widely consumed), which was called *salarium* and is the origin of the word "salary". India used cattle. Virginia used tobacco. Carolina used rice. Africa used cowry shells. Brazil used sugar. Mongolia used tea. Anything can be "money" as long as enough people accept it in exchange for their goods and services. Money does not have to be backed by a government to be considered money. Commodities have limitations: storage issues, difficult to transport over long distances, no universal acceptability, and perishability.

**Metallic money**: It's a form of commodity money. Metals (like gold) are valuable, durable, divisible, fungible, homogeneous, scarce, and it's easy to verify its purity. However, they are heavy.

**Gold backed IOUs (Non-legal tender paper currency): To prevent theft, people would leave their gold with a goldsmith, who accepts it for a fee and issues a IOU (I Owe You) note. Anyone with a IOU note can retrieve the gold from the goldsmith. Eventually, IOU notes were accepted as payments. These goldsmiths eventually realized that not everybody claimed their gold at one time, and they had a healthy balance of gold, so they started creating fake IOU notes not backed with any gold. The ratio of gold obligated to repay and the actual gold they had in the vault kept deteriorating and, occasionally, the goldsmiths disappeared overnight along with all the gold, making IOU notes worthless.

**Legal tender coinage**: Fraudsters used metallic money to cheat the public in purity or weight (mix precious metals with less precious metals). The governments decided to solve this by taking control of metallic money minting and stamping them with symbols that guarantee their weight and purity. Problem: it was centralized. Governments ended up debasing the currency (mixing precious metals) whenever they needed money, which increased money supply, decreased value of precious metals in the coins, hurt trust in the currency, deteriorates international trade, and causes domestic inflation.

**Paper money**: The oficial Chinese government currency had copper. It was difficult to use them for large transactions because they were heavy, so some people left their coins to trusted agent who would issue paper promissory notes, which could be used as a currency. It was easy to store, to transport, to carry, to divide, and was not perishable. Eventually, the Chinese emperors issued a nationwide paper currency standard backed by gold or silver that was legal tender (i.e., recognized by law as a mean to settle debt or meet financial obligations). Problem: it was centralized. Whenever the state needed money, they printed more currency, which led to oversupply and hyperinflation. The currency became worthless and China discontinued the use of paper currency in 1455. They would not adopt it again for hundreds of years.

Differences between **money** and **currency**: 

- **Money**: Item of verifiable record that is generally accepted as payment for goods and services and repayment of debts (such as taxes) in a country or socio-economic context. Main functions: medium of exchange, unit of account, store of value, standard of deferred payment (sometimes). It's intrinsically valuable and is a store of value. Example: gold.

- **Currency**: System of money (monetary units) in common use, specially for people in a nation. Monetary unit (in any form) used as a medium of exchange (usually referred to coins and banknotes). Example: dollar.

**Paper money in USA**: In 1690, the colonies started printing paper money denominated in pounds (each colony had its own). However, they printed too much, causing inflation and currencies devaluation. The British parliament ended this money printing with some "Currency acts". During the American Revolution, they states and the Continental congress issued paper money again. Soon, they printed too much and it became worthless by the end of the war. After the war, they created the current dollar, which was based on the Gold Standard (i.e., it represented actual gold and silver the government had in its vaults). But, whenever more money was needed, the government printed more money, reducing the amount of gold each dollar was worth. Many countries started cashing in dollars for actual gold, leading to the collapse of the Gold Pool. In 1971, the government ended the direct convertibility of gold to dollars (Nixon Shock), making the dollar a fiat currency.

**Fiat money**: Currency established as money by government regulation. It has no intrinsic value (no inherent utility) and is not backed by any physical commodity. It has value because parties engaging in exchange agree on its value and the government maintains its value by controlling money supply through a central bank. Virtually all countries follow this model. Problem: it's centralized and they print too much.

**Plastic money**: Money can be kept on banks and, instead of using notes, we can use plastic cards (ATM cards, debit cards, credit cards...) to spend money directly from the bank.

**Digital currencies**: People has tried to create a fully digital currency using computers and internet (like E-gold in 1996). However, it was difficult to solve the *double-spending problem* (computers make it easy to copy files, and it's not clear how to ensure that you cannot spend the same currency twice). Early digital currencies solved this by having a central organization that verifies it. This system works, but it has a single point of failure: the central organization. Hackers would target this central organization, worried governments would litigate and shut them down, and sometimes the parent company would suddenly liquidate.  

**Bitcoin**: It was needed a decentralized system that solved the double-spending problem, that could not be targeted by a government or hacker, and without a parent company. Bitcoin is a decentralized currency that solved this problem using **blockchain** and **proof of work**.

References:

- [History and evolution of money](https://lifemathmoney.com/the-history-and-evolution-of-money/)


### Bitcoin introduction

Bitcoin is a fully digital currency. There's no government issuing it, and no bank verifying transactions. Instead, there's a clever system of decentralized trustless verification based on some cryptography math.

Consider a group of people that make exchanges between each other. All exchanges are registered in a ledger. All participants maintain a ledger with all transactions in the group. The currency IS this ledger itself. Protocol:

- Anyone can add lines to the ledger
- Only signed transactions are valid
- No overspending

**Digital signatures**: To prevent fraudulend lines being added, a payer must sign his payments. Each participant has a pair **Private key** and **Public key** (two strings of bits). The public key can be known by anybody. The private key is secret and only known by this owner. 

- `sign(message, privKey) = signature`: The private key together with the message produce a signature, which is different for each message. This way, nobody can sign a message with your private key, nor produce the same signature as you. 

- `verify(message, signature, pubKey) = true/false`: The signature can be verifies using the message, signature, and public key. 

It's completely infeasable to find a valid signature without knowing the secret key (there's no better strategy than guessing and checking random signatures). A 256 bit signature has 2<sup>256</sup> possible signatures. Also, to ensure that one signed transaction is not copy-pasted, each transaction includes an id, which requires a different signature even for identical transactions.

**Decentralization**: Each participant holds their own copy of the ledger, which removes the need of trust. When A pays something to B, this transaction is broadcasted into the world, so everybody put it into their ledgers. 

**Hash function**: Function that takes an input (any kind of message) and outputs a string of bits of fixed length (called hash, or digest) that looks random. It always gives the same output for the same input. The slightest change of the input produce a completely different unpredictable output.

- **Cryptographic hash function**: Hash function where reversing the process (converting hash to input) is infeasible. The only way would be to guess and check inputs. Example: `SHA256()` produces a hash of 256 bits.

**Proof of work** (PoW): How to ensure that everybody receive the same transactions in the same order? Basically, we trust the ledger that has the most computational work put into it. This also makes fraudulent transactions and conflicting ledgers require an infeasible amount of computation to bring about. 

- At the end of a list of transactions (block) we put a number (called PoW) and encrypt the block with a cryptographic hash function. This PoW have to make the hash begin by a certain number of zeros. To find out the PoW we have to guess and check a lot of numbers until we get the hash we look for. The probability of finding a number that produces 30 heading zeros is 1/2<sup>30</sup>. 

- Finding the PoW is expensive, but verifying it is easy. This work is intrinsically tied to the list of transactions. Modifying one transaction changes the hash completely, which also requires to compute the PoW again.

- The number of zeros a PoW must create is changed periodically so it takes 10 minutes on average to find a new block.

**Blockchain**: Data structure of the ledger. Each valid block of transactions has a PoW at the end. To ensure the order of the blocks, each block also contains the hash of the previous block at its header. So, if somebody wants to modify a block, he will need to compute the PoW of that block and the following ones. When somebody finds out the block's PoW, he broadcasts the block to the rest of the world so everybody copy it to the blockchain. You can check blocks information at [BlockExplorer](https://blockexplorer.one/).

**Miners**: Those creating new blocks, looking for a **block reward** and **fees**. Not everybody are miners. Those making transactions just listen for blocks broadcasted by miners and update their own personal copies of the blockchain. If you hear two distinct blockchains with conflicting transaction histories, you take the longest one (who has the most work put into it). If they have the same length, just wait until one of them is longer. This provides a decentralized consensus (we don't trust a central authority but computational work). 

- **Block reward**: The one who finds the PoW gets a **block reward** (he's allowed to put a special non-signed transaction at the top of the block were he gets some money from nobody), incrementing the total money supply.

- **Transaction fee**: When you make a transaction, it can optionally include a fee with it that will go to the miner that includes your transaction in a block. Each block is limited to ~2400 transactions (Visa is capable of handling >24.000/s), which is slow and makes for bigger fees.

Fraud example: Imagine miner A wants to fool B by sending him a block with A paying something to B. The other miners won't be aware of this payment. For A to keep the fraud alive, he would have to keep finding the subsequent PoWs faster than the other miners so his blockchain is longer (only possible with >50% of computing power).

**Bitcoin protocol**: The ledger is the currency (it is functional per se, without needing to transform it to another currency). It's based on digital signatures and a PoW. The data structure of the ledger is the blockchain. It's decentralized.

References:

- [How does BTC actually work?](https://www.youtube.com/watch?v=bBC-nXj3Ng4)


### Cryptography

**Hash function**: Function that takes an input (message) of arbitrary length, transforms it, and outputs a value (digest, hash, tag, fingerprint) of fixed length (example: HASH-256 function outputs a 256 bit digest). It's a deterministic function (i.e., the output will always be the same for a given input).

**Cryptographic hash function**: It's a hash function design for applications that require cryptography, security, privacy confidentiality, or authentication. Some of the most common ones are **MD5** (and predecessors like MD4) and **SHA-256** (and predecessors like SHA-1). They are key building blocks in many algorithms and protocols, which are critical in many applications: digital signatures (in bitcoin, e-commerce protocols, …), message authentication protocols, pseudorandom number generation, password security, encryption, etc. 

**Digital signature** use cryptographic hash functions that must be:

- Computationally efficient: Fast to compute.
- Collision resistant: It must be astronomically hard to find two inputs that map to the same output.
- It must hide any information about the inputs.
- Output must be well distributed. It must look random. It must not be predictable. It must look unrelated to the input.

There's no mathematical proof that these techniques are secure. We trust them based on how long they've been around.






References:

- [Bitcoin - Cryptographic hash function](https://www.youtube.com/watch?v=0WiTaBI82Mc)
- [How secure is 256 bit security?](https://www.youtube.com/watch?v=S9JGmA5_unY)
- [Public key cryptography](https://www.youtube.com/watch?v=GSIDS_lvRv4)
- [What are digital signatures?](https://www.youtube.com/watch?v=s22eJ1eVLTU)
- [The GNU privacy handbook](https://gnupg.org/gph/en/manual.pdf)




References:

- []()
- []()




## Ethereum and smart contracts
## Web3
## DeFi
## Privacy coins

## References

- Harsh Strongman (2022) *Teach yourself crypto*. Retrieved from [teachyourselfcrypto.com](https://teachyourselfcrypto.com/). 