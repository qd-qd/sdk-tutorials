---
title: "Exploring the Features of Cosmos"
order: 6
description: How does Cosmos fit in the overall development of blockchain technology?
tag: fast-track
---

# Exploring the Features of Cosmos

For a long time, blockchain application developers were faced with a painful trade-off: general-purpose chains (Ethereum) are application-inclusive but are limited to simplistic use cases, while application-specific chains offer greater complexity but narrow the range of utility. This raised the question, _is it possible to build a platform for **all** use cases that does away with the limitations of general-purpose chains?_ Thanks to Cosmos, the answer is "Yes".

<HighlightBox type="learning">

This section will cover:

* The objectives of Cosmos.
* How Cosmos fits into the general development of blockchain.
* How Cosmos provides an internet of blockchains.
* How Cosmos solves the scalability issue.
* How Cosmos promotes sovereignty.
* How Cosmos improves user experience.

</HighlightBox>

## The objectives of Cosmos

The story of blockchain is one of evolution. Initial public, general-purpose blockchains were, taken as a whole, an explosive success, but did not always appeal to the need for privacy in certain industries, so a push towards private, or managed, chains followed. This was envisioned to make blockchain technology more attractive to private business enterprises. 

Now the ongoing quest for complex decentralized applications (dApps) demands a more flexible development environment than can be achieved by forking and recoding existing chains. Dividing a single blockchain's network resources between multiple dApps potentially impedes them all; so does being constrained by the general governance rules of that chain, regardless of the needs and characteristics of the dApps themselves.

This is where Cosmos steps in.

The founding **vision** of Cosmos is to provide an easy development environment for blockchain technology. Cosmos wants to address the main issues of previous blockchain projects and provide interoperability between chains to foster an **internet of blockchains** of purpose-built, or application-specific, blockchains tailored to the necessities of particular use cases and applications to coexist.

Cosmos aims to bring the following to the world of blockchain technology:

* A better decentralized application (dApp) user experience
* A simplified, specialized dApp development experience
* Facilitated scalability
* Increased sovereignty
* Speed and fast finality
* An internet of blockchains

## How Cosmos fits into the general development of blockchain

You can find the building blocks of blockchain technology in the 1980s and 1990s when breakthroughs in computer science and cryptography laid the necessary groundwork. This included append-only, provably correct transaction logs using built-in error checking; strong authentication and encryption using public-key cryptography; mature theories of fault-tolerant systems; a widespread understanding of peer-to-peer (P2P) systems; the advent of the internet and ubiquitous connectivity; and powerful client-side computers.

In 2008, **Bitcoin** changed the landscape by establishing blockchains as the foundation for decentralized networking. The development of decentralized applications built on blockchain networks began shortly after Bitcoin's debut, but in the early days developing dApps could be done only by forking or building on the monolithic Bitcoin codebase. In addition to limited scripting languages, this made dApp development a tedious and complex process for developers.

After the introduction of Bitcoin, several so-called public chains were launched, most significantly including Ethereum in 2015. Ethereum can be seen as a response to the difficulties of developing applications on Bitcoin: its application layer is the **Ethereum Virtual Machine** (EVM), which runs smart contracts. Ethereum provides a single chain on which to deploy all sorts of code for a variety of use cases.

Even though the launch of Ethereum and the EVM was a big step forward, some issues of public, general-purpose blockchains remained: mainly, low flexibility for developers and difficulties with speed, throughput, scalability, state finality, and sovereignty.

In 2014, Jae Kwon invented the original Tendermint mechanism in part as a response to this difficulty. Later in 2015, Ethan Buchman and Kwon began working together and jointly founded Tendermint Inc by the end of the year. In 2016, Kwon and Buchman founded the Cosmos network with its consensus algorithm, [Tendermint](https://tendermint.com/).

Initially, Cosmos was an open-source community project built by the Tendermint team. Since then, the **Interchain Foundation (ICF)** has assisted with the development and launch of the network. The ICF is a Swiss non-profit that raised funds in 2017 to finance the development of open-source projects building on the Cosmos network.

## How Cosmos provides an internet of blockchains

Cosmos is a **network of interoperable blockchains**, each implemented with different properties suitable for their individual applications. Cosmos lets developers create blockchains that:

* **Maintain sovereignty** free from any "main chain" governance.
* Have **fast transaction processing**.
* Are **interoperable**.

With Cosmos a multitude of use cases becomes feasible.

To achieve this vision and type of network, the ecosystem relies on an **open-source toolkit**, including the [Inter-Blockchain Communication (IBC) Protocol](https://ibcprotocol.org/), the [Cosmos SDK](https://v1.cosmos.network/sdk), and the [Tendermint consensus](https://tendermint.com/) as the base layer providing distributed state finality. A set of modular, adaptable, and interchangeable tools helps to not only quickly spin up a blockchain but also facilitates the customization of secure and scalable chains.

<ExpansionPanel title="What is the structure of a blockchain?">

Blockchain protocols define how the state is held and modified according to the received inputs. The inputs are called transactions.

The consensus mechanism ensures that a blockchain has a canonical transaction history. Blockchain transactions must be deterministic, meaning there is only one correct interpretation. The blockchain state is also deterministic: if you begin with the same genesis state and replicate all changes, you always achieve the same state.

A blockchain architecture can be **split into three layers**:

* **The network layer:** tasked with discovering nodes and propagating transactions and consensus-related messages between single nodes.
* **The consensus layer:** runs the consensus protocol between the single nodes of a peer-to-peer (P2P) network.
* **The application layer:** runs a state machine that defines the application's state and updates it with the processing of transactions implementing the network's consensus.

This layered model can be applied to blockchains generally.

Delivering consistency and ease of development for the network and consensus layers is key to achieving interoperability, and doing so frees developers to work on the application layer and deliver unique products.

</ExpansionPanel>

<ExpansionPanel title="What does a blockchain need to achieve?">

To generalize, there are three concerns any blockchain must resolve: **speed**, **throughout**, and **state finality**.

In the world of blockchains, "speed" means **transaction speed**, i.e. the time it takes to confirm a transaction. Speed is naturally impacted by the target delay between blocks, and also by the backlog of equally worthy pending transactions all competing to be included in new blocks.

**Throughput** describes how many transactions the network can handle per unit of time. Throughput can be limited for reasons of physical network bandwidth, computer resources, or even by decisions embedded in the protocol. Not all dApps have the same throughput requirements, but they all have to make do with the _average_ resulting throughput of the platform itself if they are implemented on a general-purpose blockchain. This impacts the **scalability** of dApps.

**State finality** is an additional concern. Finality describes whether and when committed blocks with transactions can no longer be reverted or revoked. It is important to differentiate between:

* **Probabilistic finality:** this implies at least the chance that changes can be made to the record, even if that chance is mathematically infinitesimal.
* **Absolute finality:** this implies no possibility of change at all, as the name suggests.

</ExpansionPanel>

Cosmos' application blockchains are built with the Cosmos SDK, which allows easy chain creation and ensures certain standards. The Cosmos SDK includes the prerequisites that make it possible for blockchains to participate in inter-chain communications using the Inter-Blockchain Communication (IBC) Protocol. Chains built with the Cosmos SDK use the Tendermint consensus. Each of these topics is unfolded in more detail in the sections that follow.

## How Cosmos solves the scalability issue

Scalability is a key challenge of blockchain technology. Cosmos allows applications to scale to millions of users. This degree of scalability is possible as Cosmos addresses **two types of scalability**:

* **Horizontal scalability:** scaling by adding similar machines to the network. When *scaling out*, the network can accept more nodes to participate in the state replication, consensus observation, and any activity that queries the state.
* **Vertical scalability:** scaling by improving the network's components to increase its computational power. When *scaling up*, the network can accept more transactions and any activity that modifies the state.

In a blockchain context, vertical scalability is typically achieved through the optimization of the consensus mechanism and applications running on the chain. On the consensus side, Cosmos achieves vertical scalability with the help of the Tendermint BFT, which currently finalizes new blocks every seven seconds. The only remaining bottleneck is then the application running on its chain.

The consensus mechanism and application optimization of a blockchain can only take it so far. To overcome the limits of vertical scalability, the multi-chain architecture of Cosmos even allows for **one application to run in parallel** on different but coordinated chains, whether operated by the same validator set or not. This inter-chain, horizontal scalability theoretically allows for infinite vertical-like scalability, minus the coordination overhead.

## How Cosmos promotes sovereignty

Applications deployed on general-purpose blockchains all share the same underlying environment. When a change in the application needs to be made, it not only depends on the governance structures of the application but also on that of the environment. The feasibility of implementing changes depends on the governance mechanisms set by the protocol on which the application is built. The chain's governance limits the application's sovereignty. For this reason, it is often called a **two-layer governance**.

For example, an application on a typical blockchain can have its governance structure, but it exists atop the blockchain's governance, and chain upgrades can potentially break applications. Independently of the dApp's governance needs, developers must come to terms with the underlying chain's governance. Application sovereignty is therefore diminished in two-layer governance settings.

Cosmos resolves this issue as developers can build a blockchain tailored to the application. There are no limits to the application's governance when every chain is maintained by its own set of validators. Cosmos follows a **one-layer governance design**.

## How Cosmos improves user experience

In the world of traditional general-purpose blockchains, application design and efficiency are limited for developers. In the Cosmos universe, the standardization of architecture components combined with the provided customization opportunities and modular design principles frees up the possibility for an unconstrained, seamless, and intuitive user experience.

It becomes easier for users to navigate between different blockchains and applications, as the same ground rules apply due to the standardization of components and application development across chains is facilitated. Cosmos makes the world easier for developers while making dApps more user-friendly. Cosmos enables sovereignty with interoperability.

## Further learning

* Take a look at the 2016 [Cosmos Whitepaper](https://v1.cosmos.network/resources/whitepaper) to find out more about the origins of Cosmos.
* ???
* ???

## Next up

This concludes Chapter 2 of the Onboarding Course! It has looked in a general way at the mechanisms of how blockchain works, as well as introduced the core features of Cosmos. 

Chapter 3 takes you on a deep dive into more technical aspects of blockchain technology, which is then expanded in [Chapter 4](ADD LINK HERE) with a closer technical look at Cosmos and some use cases of projects that take advantage of the Cosmos Ecosystem.

Before you continue to [Chapter 3](ADD LINK HERE), it is recommended to take a look at [the Chapter 2 Resource Bank](ADD LINK HERE). Then you can take a short [self-assessment test](ADD LINK HERE) to see how comfortable you are with the information you have received so far.
