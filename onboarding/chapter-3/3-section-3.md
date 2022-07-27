---
title: "Deployment Patterns"
order: 4
description: A deeper dive into decentralization and public and managed chains
tag: deep-dive
---

# Deployment Patterns

Blockchain was developed as a **decentralized technology** that allows the operation of an infrastructure without hierarchy or authority. A closer look at decentralization helps understand why it is a main criterion to distinguish deployment patterns.

<HighlightBox type="learning">

This section will cover:

* Measuring decentralization
* Deployment patterns
* Public networks
* Managed networks
* Why use managed blockchains?

</HighlightBox>

## Measuring decentralization

In [Chapter 1](ADD LINK HERE), you looked at the differences between centralized, decentralized, and distributed networks, and the claim was made that a given network could incorporate elements of all three categories. If this is the case, how can the extent of decentralization be measured?

<ExpansionPanel title="Measuring decentralization – the minimum Nakamoto coefficient">

The _**Gini coefficient**_ and _**Lorenz curve**_ are often proposed as means to quantitatively measure decentralization. Another useful tool is the _**minimum Nakamoto coefficient**_, as proposed by Balaji S. Srinivasan and Leland Lee, who argue that quantifying decentralization is not only important for purposes of measurement but also of system optimization.

**The minimum Nakamoto coefficient**

The _**minimum Nakamoto coefficient**_ quantifies the number of entities that must be compromised in order to compromise the system as a whole. The higher the coefficient, the higher the number of entities required to compromise the system.

Srinivasan and Lee argued that decentralization of *subsystems* is essential to that of the overall system. This "multi-dimensionality" of decentralization encourages taking a broader view when analyzing decentralization and thinking of possible network vulnerabilities.

To better illustrate the concept of systems and subsystems, **Bitcoin** is a fitting example. Srinivasan and Lee identified six Bitcoin subsystems:

* Mining (by reward)
* Client (by codebase)
* Developers (by commits)
* Exchanges (by volume)
* Nodes (by country)
* Ownership (by addresses)

From this perspective, it is only through the decentralization of these subsystems that the larger Bitcoin network can be considered decentralized. The extent to which subsystems are decentralized should therefore be recognized and understood.

<HighlightBox type="note">

Subsystems can differ from the ones mentioned above, and can be chosen freely as long as they fulfill the criterion of being **essential to the decentralization of the whole system**.

</HighlightBox>

Now, that you revised decentralization conceptually, it is time to consider deployment patterns in blockchain technology.

</ExpansionPanel>

## Deployment patterns

There are several mechanisms essential to ensure the working of a blockchain, like the consensus algorithms used to determine a well-ordered state of transactions and ensure network security. However, blockchains cannot be only differentiated by the consensus mechanism included in their protocols but also by their **deployment patterns**, meaning *the general set-up of the blockchain network*.

There are **two basic different deployment patterns** for blockchains:

* Public
* Managed/private

![Public and managed network comparison](/onboarding/1-introduction-blockchain/images/comparison-public-vs-rivate.png)

**Public blockchains** represent the classic understanding of how a blockchain network is constituted: they are decentralized and allow for public access. By contrast, **managed blockchain networks** rely on the blockchain data structure but do not have to mitigate the Byzantine Generals Problem, because they operate in a predictable environment with elements of authority and hierarchy.

Managed chains are "private" in a sense because most allow for authentication, authorization, and permission of actions. Therefore, they are often more suitable for traditional businesses that want to make use of the technology for internal or collaborative purposes but do not want to operate on public networks.

**The deployment pattern chosen has major implications on the functioning of the network:** what a network is supposed to do and how it is going to fulfill the envisioned tasks depends on its deployment pattern. The main way to differentiate between blockchains is to consider their **form of access**. This refers to:

* Whether there is a distinction between users or not.
* Whether access to the blockchain is open (public) or controlled (private).

<ExpansionPanel title="Permissioned and permissionless blockchains">

The terms "private" and "permissioned" are often used synonymously; so to are "public" and "permissionless" - also referred to as *non-permissioned*. It is essential to understand the difference between these terms and what they entail.

In **permissioned blockchains**, *an individual or group of participants hold the authority to validate blocks of transactions or to participate in the consensus mechanism*. Permissioned blockchains restrict an actor's involvement in the consensus state, as well as their ability to create smart contracts or transactions. 

**Permissionless blockchains** do the opposite. Block verification, smart contract creation, and making transactions on permissionless blockchain networks are open to all members.

</ExpansionPanel>

### Public networks

The most obvious way of operating blockchain protocols comes in form of a public network. A public blockchain is characterized by **open access**. Every participant has access to data and can validate as well as add blocks. Anyone, without needing the permission of another authority, can write and read data.

![Public network](/onboarding/1-introduction-blockchain/images/public-network.png)

Because network participants are not vetted and can add to the ledger without prior approval, public blockchains incorporate ways to arbitrate discrepancies and include defense mechanisms against attacks – as a result guarding against malicious participants is not required. One beauty of the public network lies in its **self-defense** attribute. Public blockchains also benefit from demand-side economies of scale, also called **network effects**.

A proof-of-work based public blockchain network has a few **specific attributes**:

* **Accessibility**: all you need to connect is the client software and an internet connection. No AML, KYC, identity checks, or subscription payment is required.
* **No hierarchy**: all nodes are equal, meaning no individual node has more authority than another. All validators are also equal.
* **Crypto-economic incentives**: the lack of a central authority means there is no absolute defense against malicious behavior. Instead, the network usually incentivizes benevolent behavior and disincentivizes behavior that endangers the network's functioning.
* **Full decentralization**: many public networks are completely decentralized because they are non-hierarchical and fully accessible. The playing field for market participants is therefore relatively level, so traditional business models may not work as well.

The two most popular examples of functioning public networks are Bitcoin and Ethereum.

<ExpansionPanel title="Introduction to Bitcoin">

Since 2009, the most successful and popular decentralized public blockchain network has been Bitcoin. It remains the cryptocurrency with the highest market capitalization.

Bitcoin was first introduced with the publication of the original paper [*Bitcoin: A peer-to-peer electronic cash system*](https://bitcoin.org/bitcoin.pdf) (2008) by Satoshi Nakamoto. In this paper, Nakamoto describes Bitcoin as a **peer-to-peer** (P2P) version of electronic cash, using Proof-of-Work and hashing to reliably record transactions and thus establish a publicly available "chain of ownership" of the currency units across the lifetime of the network.

This **chain of ownership** is the essence of blockchain technology. With complete transparency, a user can recreate every transaction that has ever been verified back to the genesis block and confirm the order of the transactions. Ownership of every single cryptocurrency unit can be traced back through each transaction in which ownership was transferred. Thus any participant can verify new payments and make sure no double-spending is taking place.

When they are created each Bitcoin is registered to a so-called **Bitcoin address**, by picking a random private key and then computing the corresponding address. This is comparable to the different forms of secrecy that were discussed regarding public-key cryptosystems in [Chapter 2](ADD LINK HERE). 

The number of possible private keys which are valid is so high that *brute force attacks* to steal Bitcoin tokens directly are unfeasible. Moreover, Bitcoin tokens can only be spent if the owner knows the *corresponding key* and *digitally signs* the transaction so the network can verify the signing with a public key. Because transactions are announced publicly, the public key of the parties is not anonymous. In the end, one has a chain of ownership.

It is worth noting that without that private key, the owner of a Bitcoin token does not have the means to prove ownership. Therefore, losing the private key equals losing all their coins.

</ExpansionPanel>

<ExpansionPanel title="Introduction to Ethereum">

Ethereum was derived from a forking of Bitcoin. It is a distributed computing platform and operating system with smart contract features, and emerged because a range of proposals to change Bitcoin were refused by the Bitcoin community.

The most important difference compared to Bitcoin is the implementation of distributed code execution through the **Ethereum Virtual Machine (EVM)**. Through this, the Ethereum network enables the deployment of **smart contracts** as part of the data of a transaction. The implementation of such a state machine using blockchain was revolutionary in itself.

In practice, a smart contract in the EVM is an autonomous agent with an internal account. In Ethereum, smart contracts are stored on every single node. They are secure in the same sense that all information stored on the blockchain is secure, although because every node calculates all smart contracts this can lead to performance issues regarding the blockchain's speed.

As discussed in [Chapter 1](ADD LINK HERE), Ethereum has a much faster block time than Bitcoin, which means at any given time a portion of the miners will be working on already solved/old blocks. Ethereum addresses this concern by including valid blocks that are not ultimately on the canonical chain as **uncles** to increase the total difficulty of the chain, capturing the "work" that would otherwise be wasted. 

The EVM is considered "Turing complete", meaning it is effectively a computer capable of running any program. However, Turing-completeness is open to the "halting problem", which is when a program enters a loop and the computer becomes unable to proceed with other activities. This is particularly difficult to solve in distributed, hierarchy-free computing.

Ethereum's solution was to introduce **gas**, a kind of fuel-currency which is charged as a fee for performing computational steps. Every block has a maximum gas limit, which sets the number of computational steps that can be executed – just like a combustion engine, if the gas runs out then the program stops. By attaching financial costs to every step in a program and limiting the funds available, transactions that enter a loop will run out of gas, freeing the system from the halting problem.

As promising as this sounds, the technology is not without limitations. Chief among these limitations is capacity, not only in terms of transactions per second but also in terms of the complexity of transactions that can be handled by the network. Ethereum's virtual machine paradigm places limits on transaction complexity to ensure that a single contract or a single transaction does not overload the shared, distributed computer. This constraint is inherent to the design choice of using a virtual machine model.

</ExpansionPanel>

### Managed networks

Managed networks, just like public networks, rely on blockchain data structures. Unlike public blockchain networks, they do not necessarily need to mitigate the Byzantine Generals Problem, because they operate in a predictable environment with elements of authority, hierarchy, and accountability.

![Managed network](/onboarding/1-introduction-blockchain/images/managed-network.png)

Managed networks can be used in cases where elements of trust already exist between the participants. A private or managed blockchain is different from a public network because participants are known and trusted due to **access barriers**. Participants are vetted through an access control layer that governs network access. Thus, a private network does not have to rely on anonymous participants to validate transactions.

<ExpansionPanel title="An example use case - interbank settlement">

Consider a network of financial institutions. Currently, each bank runs its own legacy infrastructure. When these banks try and settle trades between their customers, their systems need to interact with each other often through several layers of third-party software. 

![Bank - Insurer - Central Bank Overview](/onboarding/1-introduction-blockchain/images/private-blockchain-01.png)

Instead, they could use blockchain technology to settle inter-bank transactions. In such a system, the banks operate a common blockchain network to which only they have access. Rather than keeping their own versions of ledgers, they operate on the same ledger.

This arrangement has no need for public access. Nor is it necessary to discourage 51%-attackers, because 100% of resources for block creation are controlled by the network. Still, the risk of attacks against the blockchain creation tools or the private corporate servers remains, with success granting an attacker control over the network's resources and the power to alter transactions as they wish.

</ExpansionPanel>

Managed networks are typically governed through traditional governance processes that are appropriate for the shared goals of the participants.

Many mechanisms vital in public blockchains are not necessary or even undesirable for private blockchain settings. Public networks are based on Game Theory and economic incentives, which means that every action is probabilistic. There is no guarantee that a transaction will be picked up, and even the integrity of the network is merely *very likely*, not 100% guaranteed.

This is often unacceptable, for example for traditional financial institutions. Still, one of the biggest expenses financial and other institutions face is the operation and maintenance of infrastructure and the costs resulting from leaks, hacks, reconciliation with trading partners, errors, and data incompatibility. For this reason, many financial firms have been looking into blockchain technology, especially managed blockchains, to try to mitigate very specific issue areas and investigate this technology as a viable alternative to existing siloed systems.

<ExpansionPanel title="Consortium blockchain networks">

A **consortium blockchain network** is an option often preferred by private enterprises, especially financial market players, to pool resources to develop a shared blockchain. A consortium might use the same protocol or infrastructure as a public blockchain, but with a few differentiating attributes:

* **Limited access**: unlike public networks, many consortium blockchain models limit access to vetted and approved participants.
* **Different consensus approaches**: because the scope of participants can be limited, crypto-economic incentives might not be necessary for a consortium blockchain network. Alternatively, the creation and verification of blocks may be executed by a limited group of authorized nodes.

</ExpansionPanel>

### Why use managed blockchains?

It is often argued that managed blockchains are not that different from traditional database networks. Still, we can ascribe them certain merits by pointing out the technical differences between traditional database networks and blockchain-based networks in more detail.

There are good reasons to use a managed network within an organization, even if it does not provide the same level of data integrity and transparency as a public blockchain network. 

Both deployment types are decentralized P2P networks, which share the distributed ledger with all network participants and synchronize it through the use of a protocol. Also, both guarantee immutability to a certain degree. However, **managed networks have several advantages compared to public blockchains, which often make them seem more fitting for private businesses**.

<ExpansionPanel title="Reasons for managed blockchains in detail">

Let us look at some of the reasons businesses opt for managed networks.

**Users and access**

All users or participants in managed networks are known. This is fundamentally different from public blockchains, in which the network is open to all participants as soon as they set up the software necessary to interact with the blockchain network. So public networks do not have **entry barriers**, whereas private ones do. Restricting entrance can be especially important to increase network privacy when dealing with sensible information.

How access to the network is granted can vary. Access can be decided by:

* A central authority
* All existing participants
* A consortium
* Other means agreed upon by the owners of the network

Managed networks also allow for restricted access for verification, as the network's owner can decide to grant verification rights selectively.
  
**Energy consumption**

With network openness comes the problem of **increasing computational power**, and with it high energy consumption. The amount of energy consumption and computational power required to maintain the consensus algorithm and a distributed ledger at a large scale has skyrocketed. This is not only costly but also a major drawback in terms of the environmental sustainability of blockchain technology.

**Privacy**

One of the most important aspects of managed blockchains concerns **privacy**. As public blockchain networks are open to all participants, the information stored on them is public too. On the one hand, this degree of "publicness" helps ensure the high degree of security attributed to blockchain networks. On the other hand, limited privacy can be an issue for business activities that work with "sensitive" information. 

For this reason, private entities often favor managed blockchain networks over public ones. By being "private", managed blockchains face different implications for their security architecture, as they do not benefit from the same security mechanisms inherent in public blockchains. Security concerns of managed blockchains are comparable to those of traditional database networks. 

**Auditability and transparency**

In cryptographically secured chains of data, once data has been added it cannot be changed without re-computing all the following hashes in the chain: blockchain data is **immutable**. This is a valuable attribute for internal record-keeping, since records cannot be changed after sign-off, either through error or through malice. By combining this with smart contract execution and the implementation of critical business processes, internal process executions could become auditable.

As data and information are introduced via transactions, it becomes easy to establish what was introduced into the network when, and by whom. This enables a more cost-efficient and reliable form of bookkeeping than conventional ones. It could also streamline compliance and auditing, as well as make reporting tasks easier. The high degree of audibility and transparency makes managed blockchains especially appealing for business activities that are strongly regulated or have to conduct regular audits.

**Governance**

Managed blockchains allow for a more tailored governance structure than public blockchain networks. Not only can one limit access for participants and verification authorities, but all other aspects related to **user rights and network governance** can be limited as well. This can be very useful depending on the information you wish to store on a network.

Furthermore, platforms that allow for **smart contract execution** enable organizations to implement even more blockchain-based business operations. Processes can be encoded and their execution can be guaranteed and enforced, ideal for compliance-critical processes, or within subsidiaries with unreliable staff or operating in corrupt jurisdictions.

As information is shared and transactions are signed, it is easier to attribute an action to someone and thereby increase the overall transparency of activities. Companies can analyze processes in near real-time and check for worrisome behavior, enforce company guidelines and rules, and ensure reliable compliance control.

</ExpansionPanel>

### Public vs private/managed

Often private and public blockchain network differences are explained by using an analogy: the difference between the intranet and the internet in the 1990s, with public blockchains compared to the internet and private ones to the intranet.

The difference between both deployment types becomes visible in direct comparison. It is of importance to understand the differences as well as the implications resulting from this difference to better assess what type of blockchain is useful for what situation and/or task.

![Public and managed network comparison](/onboarding/1-introduction-blockchain/images/public-vs-private-comparison-table.png)

In summary, managed networks enable high-performance blockchain networks, which can use consensus processes that are not suited for an environment with anonymous users. A known group can create a small network for their own purposes and agree on equitable participation in the block-generation process, minimum performance metrics for acceptable validators, and governance enabling fast confirmation and even deterministic transaction finality. The principal trade-off for this performance improvement is the shunning of permissionless, public access.

Different deployment patterns have their benefits and drawbacks. They are also more or less suited to different intended network functions. **Cosmos** can be applied to both public *and* private settings and, importantly, *supports communication between networks following different consensus rules*, a seemingly intractable challenge for the predecessors of Cosmos.

Next you will take a deeper dive into the features of these alternative approaches.

## Further learning

* If you are interesting in learning more about Game Theory, [this is a useful overview](http://www.dklevine.com/general/whatis.htm)
* XXX
* XXX

## Next up

In the [next section](ADD LINK HERE), you will build on the knowledge from [Chapter 1](ADD LINK HERE) with a more detailed exploration of smart contracts.
