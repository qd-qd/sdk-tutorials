---
title: "Exploring the features of Cosmos"
order: 6
description: How does Cosmos fit in the overall development of blockchain tech?
tag: fast-track
---

# Exploring the features of Cosmos

For a long time blockchain application developers were faced with a painful trade-off. General-purpose chains are application-inclusive but are limited to simplistic use cases, while application-specific chains offer greater complexity but narrow the range of utility. This raised the question, *is it possible to build a platform for *all* use cases that does away with the limitations of general-purpose chains?* Thanks to Cosmos, the answer is "Yes".

<HighlightBox type="learning">

This section will cover:

* The Objectives of Cosmos
* How Cosmos fits into the general development of blockchain
* How Cosmos provides an internet of blockchains
* How Cosmos solves the scalability issue
* How Cosmos promotes sovereignty
* How Cosmos improves user experience

</HighlightBox>


## The Objectives of Cosmos

The story of blockchain is one of evolution. Initial public blockchains were, taken as a whole, an explosive success, but did not always appeal to the need for privacy in certain industries, so a push towards private, or managed, chains followed. Now the ongoing quest for complex decentralized applications demands a more flexible development environment than can be achieved by forking and recoding existing chains. This is where Cosmos steps in.

The founding **vision** of Cosmos is to provide an easy development environment for blockchain technology. Cosmos wants to address the main issues of previous blockchain projects and provide interoperability between chains to foster an **internet of blockchains**, allowing purpose-built blockchains tailored to the necessities of particular use cases and applications to coexist and .

Cosmos aims to bring the following to the world of blockchain technology:

* A better decentralized application (dApp) user experience
* A simplified, specialized dApp development experience
* Facilitated scalability
* Increased sovereignty
* Speed and fast finality
* Establish "an internet of blockchains"


## How Cosmos fits into the general development of blockchain

You can find the building blocks of blockchain technology in the 1980s and 1990s, when breakthroughs in computer science and cryptography laid the necessary groundwork. This included append-only, provably correct transaction logs using built-in error checking; strong authentication and encryption using public keys; mature theories of fault-tolerant systems; a widespread understanding of peer-to-peer (P2P) systems; the advent of the internet and ubiquitous connectivity; and powerful client-side computers.

In 2008 **Bitcoin** changed the landscape by establishing blockchains as the foundation for decentralized networking. The development of decentralized applications built on blockchain networks began shortly after Bitcoin's debut, but in the early days developing dApps could be done only by forking or building on the monolithic Bitcoin codebase, and limited scripting language made dApp development a tedious and complex process for developers.

After the introduction of Bitcoin, several so-called public chains came into being, the first being Ethereum in 2013. Ethereum can be seen as a response to the difficulties of developing applications on Bitcoin: its application layer is the **Ethereum Virtual Machine** (EVM), which runs smart contracts, thereby providing a single chain on which to deploy all sorts of programs for a variety of use cases. 

Even though the launch of Ethereum and the EVM was a big step forward, some issues of public, general-purpose blockchains remained: low flexibility for developers and difficulties with speed, throughput, scalability, state finality, and sovereignty.

In 2014, Jae Kwon invented the original Tendermint mechanism in part as a response to this difficulty. Later in 2015, Ethan Buchman and Kwon began working together and jointly founded Tendermint Inc by the end of the year. In 2016 Kwon and Buchman founded the Cosmos network with its consensus algorithm, [Tendermint](https://tendermint.com/).

Initially Cosmos was an open-source community project built by the Tendermint team. Since then, the **Interchain Foundation (ICF)** has assisted with the development and launch of the network. The ICF is a Swiss non-profit that raised funds in 2017 to finance the development of open-source projects building on the Cosmos network.


## How Cosmos provides an internet of blockchains

Cosmos is a **network of interoperable blockchains**, each implemented with different properties suitable for their individual use cases. Cosmos lets developers create blockchains that:

* **maintain sovereignty** free from any "main chain" governance
* have **fast transaction processing**
* are **interoperable**

With Cosmos a multitude of use cases becomes feasible.

To achieve this vision and type of network, the ecosystem relies on an **open-source toolkit**, including the [Inter-Blockchain Communication (IBC)](https://ibcprotocol.org/) protocol, its implementation in the [Cosmos SDK](https://v1.cosmos.network/sdk), and [Tendermint](https://tendermint.com/) as the base layer providing distributed state finality. A set of modular, adaptable, and interchangeable tools helps not only to quickly spin up a blockchain but also facilitates the customization of secure and scalable chains.

<ExpansionPanel title="What is the structure of a blockchain?">

Blockchain protocols define programs that hold a state and describe how to modify the state according to the received inputs. The inputs are called transactions.

The consensus mechanism ensures that a blockchain has a canonical transaction history. Blockchain transactions must be deterministic, meaning there is only one correct interpretation. The blockchain state is also deterministic. If you begin with the same genesis state and replicate all changes, you always achieve the same state.

A blockchain architecture can be **split into three layers**:

* **The network layer**: tasked with discovering nodes and propagating transactions and consensus-related messages between single nodes.
* **The consensus layer**: runs the consensus protocol between the single nodes of a peer-to-peer (P2P) network.
* **The application layer**: running a state machine that defines the application's state and updates it with the processing of transactions implementing the network's consensus.

This layered model can be applied to blockchains generally. Delivering consistency and ease of development for the network and consensus layers is the key to achieving interoperability, and doing so frees developers to work on the application layer and deliver unique products.

</ExpansionPanel>

<ExpansionPanel title="What does a blockchain need to achieve?">

To generalize, there are three concerns any blockchain must resolve: **speed**, **throughout**, and **state finality**.

In the world of blockchains, "speed" means **transaction speed**, the time it takes to confirm a transaction. Speed is naturally impacted by the target delay between blocks, and also by the backlog of equally worthy pending transactions all competing to be included in new blocks.

**Throughput** describes how many transactions the network can handle per unit of time. Throughput can be limited for reasons of physical network bandwidth, computer resources, or even by decisions embedded in the protocol. Not all dApps have the same throughput requirements, but they all have to make do with the _average_ resulting throughput of the platform itself if they are implemented on a general-purpose blockchain. This impacts the **scalability** of dApps.

**State finality** is an additional concern. Finality describes whether and when committed blocks with transactions can no longer be reverted or revoked. It is important to differentiate between *probabilistic* and *absolute finality*: probabilistic finality implies at least the chance that changes can be made to the record, even if that chance is mathematically infinitesimal, whereas absolute finality implies no possibility of change at all, as the name suggests.

</ExpansionPanel>

Cosmos' application blockchains are built with the Cosmos SDK. The Cosmos SDK includes the prerequisites that make it possible for created blockchains to participate in inter-chain communications using the Inter-Blockchain Communication Protocol (IBC). Chains built with the Cosmos SDK use the Tendermint consensus. Each of these topics is unfolded in more detail in the sections that follow.


## How Cosmos solves the scalability issue

Scalability is a key challenge of blockchain technology. Cosmos allows applications to scale to millions of users. This degree of scalability is possible as Cosmos addresses **two types of scalability**:

* **Horizontal scalability**: scaling by adding similar machines to the network. When *scaling out*, the network can accept more nodes to participate in the state replication, consensus observation, and any activity that queries the state.
* **Vertical scalability:**: scaling by improving the network's components to increase its computational power. *Scaling up*, the network can accept more transactions and any activity that modifies the state.

In a blockchain context, vertical scalability is typically achieved through the optimization of the consensus mechanism and applications running on the chain. On the consensus side, Cosmos achieves vertical scalability with the help of the Tendermint BFT. The Cosmos Hub currently conducts transactions in seven seconds. The only remaining bottleneck is then the application.

The consensus mechanism and application optimization of a blockchain can only take it so far. To overcome the limits of vertical scalability, the multi-chain architecture of Cosmos allows for **one application to run in parallel** on different but coordinated chains, whether operated by the same validator set or not. This inter-chain, horizontal scalability theoretically allows for infinite vertical-like scalability, minus the coordination overhead.


## How Cosmos promotes sovereignty

Applications deployed on general-purpose blockchains all share the same underlying environment. When a change in the application needs to be made, it not only depends on the governance structures of the application but also on that of the environment. The feasibility of implementing changes depends on the governance mechanisms set by the protocol on which the application builds. The chain's governance limits the application's sovereignty. For this reason it is often called a **two-layer governance**.

For example, an application on a typical blockchain can have its governance structure, but it exists atop blockchain governance, and chain upgrades can potentially break applications. Independently of the dApp's governance needs, developers must come to terms with the underlying chain's governance. Application sovereignty is therefore diminished in two-layer governance settings.

Cosmos resolves this issue as developers can build a blockchain tailored to the application. There are no limits to the application's governance when every chain is maintained by its own set of validators. Cosmos follows a **one-layer governance design**.


## How Cosmos improves user experience

In the world of traditional general-purpose blockchains, application design and efficiency are limited for blockchain developers. In the Cosmos universe the standardization of architecture components combined with the provided customization opportunities frees up the possibility for an unconstrained, seamless, and intuitive user experience.

It becomes easier for users to navigate between different blockchains and applications, as the same ground rules apply due to the standardization of components. Cosmos makes the world easier for developers while making dApps more user-friendly. Cosmos enables sovereignty with interoperability!


## Further learning

* Take a look at the 2016 [Cosmos Whitepaper](https://v1.cosmos.network/resources/whitepaper) to find out more about the origins of Cosmos.
* ???
* ???


## Next up

XXXXXXX