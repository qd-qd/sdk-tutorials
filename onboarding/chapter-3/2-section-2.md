---
title: "Consensus Mechanisms"
order: 3
description: A deeper dive into forming consensus in decentralized networks
tag: deep-dive
---

# Consensus Mechanisms

This section recaps and builds on the examination of [blockchain consensus mechanisms in Chapter 2](ADD LINK HERE), and addresses several issues arising from how consensus is achieved.

<HighlightBox type="learning"> 

This section will cover:

* Consensus mechanisms
* Eventual consensus
* Forking
* Immutability
* Block creation and finality
* General types of consensus algorithms

</HighlightBox> 

As is now well established, blockchain is a well-ordered set of data on which all peers agree. What they agree on is considered the **single truth** – reached by consensus, this means the *single true state of the distributed ledger*.

**Consensus has to be reached to guarantee data consistency.** However, achieving an agreement across a network of active peer nodes is an *eventual* process, and this has implications for the particular approach taken to implement blockchain technology.

![Blockchain as a consensus network](/onboarding/1-introduction-blockchain/images/blockchain-as-a-consensus-network.png)

## Consensus mechanisms

**Consensus** can be understood as *a process in which the network, constituted by nodes, reaches an agreement regarding the order of transactions and validates proposed blocks*. Consensus mechanisms generate:

* Consensus on the global **state of the blockchain**
* Consensus on a **set of transactions** in a block

The main functions of such mechanisms are to:

* **Order transactions.**
* **Validate transactions.**

<HighlightBox type="info">

Consensus algorithms establish **safety** and **liveness** by generating consensus, ordering transactions, and validating them.

**Safety** requires the algorithm to behave like a single node system would: executing each transaction atomically one at a time. The same set of transactions should lead to the same changes in the state on each node.

**Liveness** refers to the upholding of network synchronization: all non-faulty nodes will eventually receive every submitted transaction.

</HighlightBox>

## Eventual consensus

To understand consensus in blockchain technology, remember that the truth is the state all participants agree upon. Consensus is eventual in blockchain because blocks are created as transactions are performed. Thus, what is agreed upon depends on the operations taking place.

Take a look at why eventual consensus is important and how consensus is reached in case of competing claims.

### The CAP Theorem

The **CAP Theorem**, also known as *Brewer's theorem* after Eric Brewer, states that in a distributed system you can at most achieve two guarantees out of the following three:

* **Consistency:** each node on the network *always holds the most up-to-date data*.
* **Availability:** any data request to the network *always receives a response*.
* **Partition tolerance:** the network is *always operational*, even when a subset of nodes is failing.

**Partition tolerance** is a given fact in distributed networks. Blockchains are decentralized, and therefore operational even when several nodes are not. Therefore, only the trade-off between *consistency* and *availability* needs to be considered when designing a network. What do the alternate options signify?

* **Choosing availability over consistency** means that the distributed system is always operational and data requests always receive a response, but a responding node could be holding outdated data.
* **Choosing consistency over availability** means the distributed system is always operational and every node's data is always up to date, but the system could fail to respond when a request is made.

In blockchain **availability** is essential, as the state has to be accessible to all nodes. If a blockchain system prioritized consistency over availability, in the event of any connectivity issue or of failing nodes unanswered requests become a possibility and some transactions would no longer be made. For this reason, availability is usually chosen over consistency as part of the foundations of the general architecture.

However, consistency is not out of reach for a distributed network. Blockchain networks can achieve all three properties of the CAP Theorem *over time* by focusing on availability and partition tolerance and reaching ***eventual* consistency** through consensus algorithms.

While this allows blockchains to satisfy all the key demands a network might have, the eventual nature of consensus and consistency can lead to a form of partitioning event known as **forking**. Forks are important to understand, as they can have a potentially undesirable or unwanted impact on a network.

## Forking

<HighlightBox type="info">

In software engineering, **forking** describes a process in which a developer duplicates a source code to begin creating a new, independent piece of software based on that code. In blockchain, the term **forking** has added significance. The mechanism is analogous, but it is applied and intended for different purposes.

</HighlightBox>

Imagine you have a blockchain network in which two alternate new blocks are suggested for the next free position in the chain. In [Chapter 2](ADD LINK TO CH2-MOD3), this situation was visualized as ripples spreading out from the originating nodes as if stones dropped into a pool of water. It is possible that other nodes would receive competing claims about the winner, but they are unlikely to receive both claims simultaneously. The protocol selects the block with the most transactions or with the most complex puzzle solved.

However, if nodes within the network make different decisions about which of the competing blocks to accept, you then have a **fork**, or two competing truths. The chain of blocks then continues on **two different paths** in parallel: the chain of blocks splits into two strands with groups of nodes working to add new blocks to the side of the fork they are on. As each half of the fork is extended, the nodes on the network re-evaluate each chain for length and complexity and potentially decide which side of the fork to keep working with.

![Example of a fork](/onboarding/1-introduction-blockchain/images/blockchain-forking.png)

Each blockchain protocol provides a mechanism to _eventually_ choose a single branch of the fork. Forks are introduced as a **means to reach consensus even when the community does not agree to**. In the end, an eventual consensus is reached and the losing strand is replaced by the winner throughout the network, returning **consistency** to the states of all nodes.

### What can cause a fork?

Forks are often a result of changes made to the blockchain protocol (protocol upgrades) and not transactions updating the state. As a blockchain network evolves so does its protocol in ways that can be minor or major. When a block introduces a protocol change, a fork can result if it is not supported unanimously: the network separates into two groups using different versions of the blockchain protocol.

When talking about forks, it is important to note that they can be differentiated as **accidental** or **intentional**.

**Accidental forks** occur when two or more miners find a block almost at the same time, meaning each block has the same block height. This type of fork is a direct result of the decentralized network design.

**Intentional forks** are generated by either a developer or an attacker. They are used to change the rules (the protocol) of a blockchain, and are defined as either:

* **Hard forks**
* **Soft forks**

### Hard forks

A **hard fork** represents _a change in the protocol of a blockchain that is **not backward-compatible**_. This is the case when the new rules for validating are different to such an extent that the old rules would see *new-rule blocks* as invalid.

In this circumstance, all nodes would have to accept the change and implement it by using the new rules to maintain a unified rule set for validation. If a group of nodes objects to using the new rules and continues using the old ones, a fork occurs - effectively dividing the original singular network into two parallel networks.

### Soft forks

A **soft fork** represents *a change of the protocol with which the rules enforced are restricted*, thus it **is backward-compatible**. Soft forks are often used to update the blockchain's protocol.

A soft fork can also result in the chain splitting. This happens when blocks continue to be created under the *old rules* and are then regarded as invalid under the *new rules*.

<ExpansionPanel title="Forking in action - The DAO">

In [Chapter 1](ADD LINK HERE), you encountered the story of "The DAO", in which a coding flaw allowed an attacker to extract tens of millions of dollars worth of the cryptocurrency Ether. In response to this, both soft *and* hard forks were proposed as a solution.

The **soft fork proposal** would have applied an update to network clients that blacklisted the addresses of the attacker, rendering them unable to retrieve the extracted Ether. However, it later turned out that this introduced vulnerabilities into the clients that enabled distributed denial of service (DDOS) attacks to be made against them.

A second **hard forking proposal** introduced protocol changes that in practice rewrote history. It established a state in which the attack never happened, allowing the affected investors to retrieve their funds. However, this update introduced a change that made any clients that adopted it incompatible with those that did not, making it a hard fork.

When the change was activated a small group of miners deliberately refused to install the update, calling the changes a bailout and a compromise of the immutability of the network. The original Ethereum network was split, becoming **Ethereum** (which adopted the protocol change) and **Ethereum Classic** (which maintained the original protocol).

The story of The DAO provokes some questions to consider when assessing public blockchain networks:

* How will the community react to failures on the application layer?
* Who is influential in the community, and what are their interests?
* What are the professed values of the community?

</ExpansionPanel>

## Immutability 

**Immutability** refers to the *unchangeability of objects over time, or the inability to perform changes*. In the case of blockchains, once data has been included in the blockchain - by a transaction being included in a verified block of the chain - editing or deleting it is nearly impossible. The use of hashes ensures a high degree of immutability and easy tampering detection. If data is edited or removed, the block's hash and chain would fail. Changes can only be introduced using the consensus mechanism of the network.

<HighlightBox type="info">

In private databases, most end-users get read-only access. Full access is usually limited to system administrators. The organizational structure of the system is designed to prevent malicious behavior. Often, other than the organizational design, no control system ensures data immutability.

</HighlightBox>

When a new node connects to the network, or returns after being offline, it needs to download the existing blockchain state. The other peers of the network help by sending the latest block, the previous blocks, plus the list of past transactions. However, malicious nodes may decide to withhold certain transactions and, conversely, send transactions that do not appear in the blockchain on which honest nodes agreed.

How does this new node eventually reach the same consensus as the honest nodes?

<HighlightBox type="remember">

Each block of the blockchain is identified by:

* The hash of its predecessor
* The root hash of its transaction's Merkle tree
* A nonce that solves the mining puzzle
* A hash of the above

</HighlightBox>

For a malicious node to remove or insert transactions, it would need to:

* Update the root hash of the block's Merkle tree.
* Update the nonce of the containing block.
* Update the hash of the containing block.
* Do the same for all subsequent blocks.

This is theoretically possible in a Proof-of-Work (PoW) network, but in practice requires the malicious nodes to harness more processing power than the honest nodes. A node will almost certainly end up connecting to an honest node during its life. This honest node would tell the deceived node a different truth from that of the malicious nodes, after which the new node would need to make a decision. It will always decide to go with the **longest or more difficult fork**.

It is said that the blockchain is **immutable** because of the practical difficulty to include new or change old data.

## Block creation and finality

**Finality** refers to _the guarantee that transactions, blocks, and ultimately the state of the ledger cannot be altered, reversed, or manipulated after a block is validated and becomes part of the chain_. In practice, network latency influences finality. Therefore, finality is used to indicate the amount of time you have to wait to consider a transaction to have become immutable.

Finality is an essential feature of blockchains. Without it, a blockchain network cannot serve properly as a network for assets with value, payment, or an immutable ledger. However, most blockchain protocols only have **probabilistic (transaction) finality** – transactions are not automatically or *instantly* final, but become more final over time as more blocks are confirmed.

The amount of time it takes a blockchain network to confirm a transaction (latency) determines the nature of the chain's finality rate. There are different **types of finality** in blockchains, depending on the underlying consensus mechanism a protocol relies on.

<Accordion :items="
    [
        {
            title: 'Probabilistic finality',
            description: '**Probabilistic finality** applies to *PoW* protocols, and defines finality by how plausible it is that a given transaction could be modified. A transaction in the latest block of the chain *could* be changed or deleted with less work on the part of an attacker than a transaction in the previous block. Any change to blocks further down the chain would demand increasing amounts of work to validate new hash values rising up the chain, and at some point, it becomes implausible that such an attempt could succeed against the ongoing extension of the chain by the rest of the network. Probabilistic finality is *finality in effect*; not strictly speaking *impossible*, but sufficiently impractical that it can be discounted.'
        },
        {
            title: 'Absolute finality',
            description: '**Absolute finality**, or deterministic finality, is a trait of protocols based on *PoS*. In these systems, new blocks are added by an act of majority consensus amongst validating nodes, and once validators signal their approval of a block they cannot change their opinion, so there are no scenarios in which a transaction could be revoked after it has been finalized. Therefore, transaction finality is achieved as soon as a block is verified.'
        }
    ]
"/>

While absolute finality can be more desirable than probabilistic finality, there are some **trade-offs** to consider: users making payments will most probably favor absolute finality, but decentralized applications (dApps) might require availability over consistency and thus, accept probabilistic finality.

When it comes to payments, probabilistic finality opens up a network to its transactions only being more or less *probably* final, but not "*final* final" – and blocks changing could lead to the loss of millions of dollars. However, dApps might require transactions to always go through even when they include minor mistakes.

Finality largely affects the user experience. Thinking about finality is essential to developing robust blockchain platforms and choosing which platform to develop applications for.

## General types of consensus algorithms

Consensus algorithms can be differentiated into **lottery-based algorithms**, such as Proof-of-Work, and **voting-based algorithms**, for example, Delegated-Proof-of-Stake.

In lottery-based algorithms, nodes creating blocks are randomly selected in a mechanism strongly resembling a lottery. These algorithms are said to have **high scalability** but with a tendency of producing **forks** and thus **high-latency finality**. With increased block creation time, the probability of peers creating different new blocks in parallel can result in numerous forks, requiring the network as a whole to evaluate its options to achieve finality.

Voting-based algorithms bring the advantage of **low-latency finality**: finality is faster than in lottery-based algorithms. This type of algorithm also brings a **scalability/speed trade-off**: as all nodes have to be kept in the loop, the larger the network the longer it takes for consensus to be established across all nodes.

To summarize, lottery-based algorithms have good speed and scalability but are slower in achieving finality. Voting-based algorithms are fast and achieve finality faster but are not as well-suited when it comes to scalability. The suitability of algorithms depends strongly on the network requirements and different fault-tolerance models.

## Further learning

* For a good read on blockchain and the CAP Theorem, read [CryptoGraphics: CAP Theorem](https://cryptographics.info/cryptographics/blockchain/cap-theorem/).
* ???
* ???

## Next up

In the [next section](ADD LINK HERE), you will take a closer look at decentralization to see how it impacts deployment mechanisms in blockchain.
