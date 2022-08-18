---
title: "Proof-of-Work"
order: 3
description: How to trust the content of a block
tag: fast-track
---

# Proof-of-Work

The [previous section](ADD LINK HERE) looked a little deeper into the practicalities of how a reliable, distributed, append-only ledger can be implemented through the use of hashing. Now it is time to look at the methods used to make sure the information you receive is something you really can be sure about.

<HighlightBox type="learning">

This section will introduce:

* Proof-of-Work
* What is a nonce?
* Proof-of-Work in Bitcoin
* Alternative systems of proof

</HighlightBox>

Last time, you saw a very basic model for building a blockchain:

* Block 1: compile some transactions and generate a hash.
* Block 2: compile more transactions, add the hash of Block 1, and generate a new hash.
* Repeat, always adding the hash of the previous block before you generate the next.

Looks good – but there is a gap. _Who exactly creates these blocks of transactions, and how?_

## Proof-of-Work

From how blockchain has been described so far, it seems that any node in the network could compile some transactions and assert that they represent the next block in the chain – but that would be chaos in a hierarchy-free network. Information does not spread across a network uniformly, so the chance of any two nodes agreeing on exactly the same block content would be vanishingly small.

* The shared chain must contain certain blocks in a certain order.
* Each block must contain certain transactions in a certain order.
* Each transaction must be valid in the context of the state of the chain when it was made – but that will not happen in a chaotic free-for-all.

### Blocks in a chain - Speed of creation vs speed of confirmation

In a sense, making it easy to build a block is both a strength and a weakness in the context of blockchain networks. Confirming that a new block is valid *must* be a fast process or the network would grind to a halt – and new blocks can be confirmed by having each node create them *again* to make sure they get the same hash output as the original. However, if creating a block is so fast and easy the network would be perpetually swamped with alternative blocks competing to be accepted. So, how can the same process be used to achieve both goals without it being just as easy both times?

The Shakespearean ledger will explain how this is achieved. The original example took an input - the title of a play, representing the "block" of its entire text - and [applied the SHA-256 hashing function](https://www.browserling.com/tools/all-hashes) to generate a hash. In this case, use *Hamlet*:

* **Input phrase:** Hamlet
* **Output hash:** dcb17698cf832a3757ab5ad855906cac0b6db4e8ac5faff12a1562a6b6326cc5

Now, imagine there was an additional, *completely arbitrary* rule to be satisfied before this block could be added to a chain: **the output hash MUST begin with a zero character, `0`**.

How can this happen? The transactional content of the block must not change - the text of the play is valuable information and must be preserved exactly- *but the hash function is deterministic*. A deterministic model will always produce the same output from a particular input – meaning that unless *something* in the block changes, the hash never will.

To make the *Hamlet* block viable, let us introduce a new concept: *a nonce*.

## What is a nonce?

The archaic word **nonce** means "one time" or "on one occasion", and that is what you need right now: a one-time solution for this instance of creating a block. In blockchain, **the nonce** is _a random extra piece of data that changes the hash output enough to satisfy the arbitrary rule of the chain, and which, therefore "solves" the current block_.

The nonce could be literally any additional content since the slightest modification of the block's content will generate an entirely new hash output. Here is a simple illustration:

![Finding a nonce](/onboarding/chapter-2/images/Table_03.png)

With a little repetitive work, a combination of *block and nonce* has generated a hash that satisfies the `0` rule for *Hamlet* in just four attempts. However, not every block is so quick and easy. The block of *Romeo and Juliet* requires *twenty-six* tries to start with a zero:

* **Input phrase:** Romeo and Juliet 26
* **Output hash:** 094c053069fc96ff5d9f64ec1b43cad19b72148b18fa3e79acb39ce3e386c4db

### First among equals

The first digit of a hash is effectively random. As hexadecimal uses sixteen different characters there is a one-in-sixteen chance that it would be a zero – but already you can see that finding a solution can take an unpredictable amount of time, and in genuine blockchain applications the number of "leading zeros" is always bigger. A lot bigger.

Each additional leading zero significantly increases the likely number of guesses required to discover a satisfactory hash. The following table shows the number of alternatives that exist for a given number of leading zeros and how quickly the potential workload increases:

![Escalating workload](/onboarding/chapter-2/images/Table_04.png)

Identifying a viable nonce for a given block could therefore mean a lot of work, and only modern computing makes these processes possible. What is important is that hashing is a one-way functions: **there is no better way of discovering a satisfactory hash value than by choosing a random nonce and seeing what it generates**. If it does not produce the number of leading zeroes required, you have to pick a new nonce and try again. This means every node competing to propose a block of transactions to add to the chain has an equal chance of success. They do not even need to try to solve for a block including the *same* transactions in the same sequence – the chance is still equal.

Discovering a viable nonce demands a "brute force" approach, so success is considered to be evidence of significant effort or work by the winning node – or **miner**, the typical name for nodes that participate in this kind of hunt for a nonce. Adding blocks is a necessity for any blockchain to function, so the miner that succeeds in discovering the nonce and adding a new block is rewarded for their services to the network.

The nonce solves two problems. Confirming a new block is valid remains fast because now each node knows which nonce to use instead of having to discover it independently. Even if generating one hash is easy, **it requires intensive computing power to generate enough hashes to identify a valid nonce before someone else does**. Thus the same process *can* be both easy and difficult at the same time. All that is required is the elusive nonce.

This factor also limits the number of nodes attempting to create blocks for the chain. It is not *impossible* for one miner working on a regular home computer to succeed, but the chances are so small that it is not really even worth trying. The result is a manageable quantity of candidate blocks generated by those miners with the resources to realistically compete.

<HighlightBox type="info">

Exactly why is the lone miner and their regular PC unlikely to succeed? In the beginning, a home computer *was* more than sufficient, but over time the centralization of mining has become a real issue in popular PoW networks.

Nowadays, huge **mining pools** dominate block mining. Each pool has many powerful computers using specialized graphics cards capable of "crunching numbers" at much faster rate than even the most up-to-date domestic setup could hope to match.

</HighlightBox>

## Proof-of-Work in Bitcoin

This validation system, called a consensus algorithm, is the basis for many blockchain networks, first and foremost **Bitcoin**, whose mystery creator Satoshi Nakamoto proposed this **Proof-of-Work** (PoW) concept.

The number of leading zeroes required to successfully mine a Bitcoin block varies, but it is currently set at 17. This is literally a greater-than-astronomical number. For anyone desirable result, there are approximately 1.5 billion times as many alternatives as there are stars estimated to exist in the Milky Way galaxy.

With the computing resources of the Bitcoin network committed to the search for a valid nonce, the number of hashes tested reaches 1,000,000,000,000,000,000 *per second*, on average for six hundred seconds – an enormous amount of collective computing effort, which also serves to secure the network by overwhelming any attempt to manipulate the system. However, Bitcoin mining is competitive, so only one miner will be fortunate enough to find the nonce that solves the block...*and they are the only ones to be rewarded*.

PoW is a powerful counter strategy to authority-driven networks: it is a method of determining who should have the privilege of defining the canonical transaction order, if only for a brief moment, in a network that is free of hierarchies. However, mining is fundamental to Bitcoin in more ways than extending the number of blocks on the chain: success is rewarded through the **minting** of new Bitcoins, which is the *only* way new coins are added to the system.

<HighlightBox type="info">

**Mining vs Minting**

Bitcoin is a Proof-of-Work system, and as you have seen **mining** is how new blocks are validated in PoW. Because successful miners are rewarded through the creation of new Bitcoins, in PoW the term "mining" is also used to refer to the coin creation process.

However, there are alternatives to PoW which do not rely on an intensive search for a nonce, but which still reward block validation through the creation of new cryptocurrency units.

In the cryptocurrency context, **minting** simply means *the creation of new coins*, regardless of the particular proof system used by the network. It is also used in tokenization systems (like NFTs) to refer to the creation of tokens.

The term "to mint" is borrowed from traditional finance, and originally meant *the creation of physical coins by stamping them from sheets of metal*. 

</HighlightBox>

The more comprehensive each new block is, the better for the network, as this ensures the ongoing transactional record is made secure as efficiently as possible. Therefore, user-paid transaction fees are used to further incentivize miners to pack as many transactions as possible into the blocks they are trying to issue. Transactions that do not make it into a new block are not lost, of course – they are simply (loosely) queued to be picked up and packed into blocks to come. New blocks in Bitcoin are created roughly every ten minutes, so they do not have to wait long.

However, PoW also has its drawbacks. The search for a nonce is a competitive project, it would be of limited benefit if only a single miner was searching, as it could take a very long time for new blocks to be added. Instead, multiple miners must work hard *simultaneously* to achieve a goal that *only one of them will be rewarded for*. This is a winner-takes-all race: one miner wins big, but the others just burn a lot of energy to come second.

Finding the right nonce is a computationally intensive task and as such consumes a lot of energy. The extent of this energy drain has drawn significant criticism, particularly in the context of ongoing climate change, with little of the electricity used derived from renewable sources. Bitcoin's annual consumption has been estimated at 150 terawatt-hours of electricity, more than that of Argentina, a nation of 45 million people. At this point, you may ask: *is there another way?*

## Alternative systems of proof

Key to the philosophy of blockchain is the divestment of centralized authority from networks, and **Proof-of-Work** is the embodiment of that approach: any node can "win" responsibility for progressing the state of the blockchain.

However, the degree to which participants enjoy equality can vary, and different approaches employ different rules for how the distributed ledger is updated which *do* involve kinds of hierarchy established through the network's nodes. Unlike PoW these alternatives can also achieve **transaction finality**, in which blocks are immutable as soon as they are validated, which is an invaluable benefit for certain applications.

The following are popular alternatives to PoW consensus algorithms.

### Proof-of-Authority

If a Proof-of-Work system relies on acknowledged effort to progress the state of the chain, it seems obvious how a **Proof-of-Authority** (PoA) system differs. In PoA, "validator" nodes are pre-selected based on the belief that they can be trusted, so they do not need to prove themselves through nonce calculations. This drastically reduces the network's energy demands and allows for faster block times. The criticism leveled at POA is, of course, that traditional forms of systemic authoritarianism are creeping back into place.

### Proof-of-Stake

_How can you be confident that someone in a position of power has the best interests of the system at heart? What if they **personally** have a lot to lose if things go bad?_

**Proof-of-Stake** (PoS) leverages this intuitive idea: validators are pseudo-randomly selected to serve the system based on the amount of cryptocurrency they hold. If they generate blocks that are accepted by the network, they are rewarded for their work. At the same time, they face economic penalties if their blocks are rejected as other nodes are empowered to identify any bad behavior. This incentivizes validators to work towards the network's interests and aligns their interest with the best interest of the network.

### Delegated-Proof-of-Stake

An extension of the PoS concept is ***Delegated*-Proof-of-Stake** (DPoS) networks, in which the validators (or "witnesses") are effectively voted into positions of authority by other stakeholders in the system, who commit their cryptocurrency stakes to accumulate a shared stake for a given validator - delegate their stake. Validators are then selected with a frequency proportional to their total stake to collaborate on a round of block creation with other validators sufficient to represent the interests of at least 50% of the stakeholders. This is the methodology employed in the Cosmos Ecosystem.

Each validator is again rewarded or penalized based on their behavior. However, these gains and losses are also shared by any stakeholders who assigned their votes to that validator, similar to the dividends paid to shareholders of a business. Incentives for good behavior are compounded, as the status of any validator can fluctuate with their performance. If unhappy voters withdraw their support and delegate it elsewhere, the validator loses its income basis.

DPoS networks also elect "delegates", who supervise network governance and performance and propose changes that are then voted on by the entire network. DPoS is often considered superior to PoW and PoS approaches since it is fast, energy-efficient, enjoys high security and integrity, and is fundamentally democratic in nature. However, it also has high barriers to entry, and the validator sets are fixed. As in politics, you may get to choose who to vote for, but starting your own party is no easy matter.

### Practical Byzantine Fault Tolerance (pBFT)

Regular Byzantine Fault Tolerance (BFT) was mentioned in the [previous chapter](ADD LINK HERE) – in essence, it refers to a distributed network still able to function despite challenges such as malicious or failed nodes and unreliable communication. BFT means that all correctly functioning nodes form a consensus on their values successfully, and pBTF is an implementation of this concept. It works like this:

1. One node of the network is selected to be the "primary" – as mentioned, in the case of Cosmos this selection is made through DPoS.
2. The primary proposes a candidate block and broadcasts it to the validator nodes, or "replicas", requesting them to accept and sign the block, or to reject it.
3. If a majority of the validators signal their support for the block, it is finalized: support is irreversible, and because no greater consensus can now be reached there is no possibility of a competing block superseding this new canonical blockchain state.
4. The finalized block is broadcast to the network at large, updating the shared ledger.

As well as avoiding energy-intensive nonce calculation, pBFT can identify compromised nodes (even if one of these is the primary). Because multiple nodes participate in the updating process, they are all rewarded to some extent, spreading the benefits through the network. However, pBFT requires a higher level of communication across the system, so confirmation of the blockchain state is correspondingly slower than in alternative solutions, and as networks grow in size pBFT can become less viable as a solution.

## Further learning

<HighlightBox type="reading">

* ???
* ???

</HighlightBox>

## Next up

At this point, you know how the original concept of blockchain functions: a distributed ledger in which updates are validated through a Proof-of-Work system. You've also learned about some more recent developments toward alternative networking organizations – **Cosmos**, as mentioned, utilizes a combination of Delegated-Proof-of-Stake *and* pBFT as its validation model. 

In the [next section](ADD LINK HERE) the focus descends to the network level to examine the experience of updating a blockchain from the perspective of an individual node.
