---
title: "Tendermint"
order: 2
description: Exploring features of the Tendermint Core and ABCI
tag: deep-dive
---

# Tendermint

You already have some understanding of Cosmos in detail. Now it is time to look at the underlying technology: Tendermint.

<HighlightBox type="Learning">

This section will cover:

* Summarizing the Cosmos Ecosystem
* What is Tendermint?
* Consensus in the Tendermint Core and Cosmos
* Upgradeability of chains
* Application Blockchain Interface (ABCI)
* Application-level concerns

</HighlightBox>


## Summarizing the Cosmos Ecosystem

**Cosmos** is a network of independent blockchains, which are:

* All powered by consensus algorithms with Byzantine Fault-Tolerance (BFT).
* All connected through the Inter-Blockchain Communication Protocol (IBC), which enables value transfers, token transfers, and other communication between chains, all without the need to involve exchanges or make compromises regarding each chain's sovereignty.

Cosmos is also **a blockchain ecosystem** complete with protocols, SDK, tokens, wallets, applications, repositories, services and tools.


## What is Tendermint?

Tendermint is a consensus algorithm with Byzantine Fault-Tolerance (BFT) and a consensus engine. It enables applications to be replicated in sync on many machines, and the result is known as a *Replicated State Machine with Byzantine Fault Tolerance*. It guarantees BFT properties for distributed systems and their applications. It does this:

* **Securely**: Tendermint continues working even if up to 1/3 of machines fail or misbehave.
* **Consistently**: every machine computes the same state and accesses the same transaction log.

Created in 2014, [Tendermint](https://tendermint.com/) accelerated the development of distinct blockchains by providing **a ready-made networking and consensus solution**. Networking and consensus no longer had to be recreated by developers for each case.

Tendermint is widely used across the industry and is the most mature BFT consensus engine for Proof-of-Stake (PoS) blockchains. You may already be using Tendermint without being aware of it, as other blockchains like [Hyperledger Burrow](https://hyperledger.github.io/burrow/#/) and the [Binance Chain](https://www.binance.org/en/smartChain) use Tendermint.

### What does Tendermint provide?

Tendermint is a Deligated-Proof-of-Stake system based on dedicated validators with good network connectivity. This is quite different from PoW, which favors inclusion and must accommodate slower nodes with greater latency and less reliability, resulting in probabilistic finality. In relation to the CAP Theorem, Tendermint prefers consistency over availability.

**Tendermint modules attend to consensus and networking**. These are two important components of any blockchain. This frees developers to focus on the application level without descending into lower-level blockchain concerns, such as peer discovery, block propagation, consensus, and transaction finalization. Without Tendermint, developers would be forced to build software to address these concerns which would add additional time, complexity, and cost to the development of their applications.

![Blockchain application architecture overview](/architecture_overview.png)

A blockchain node for an application-focused Cosmos blockchain consists of a state-machine, built with the Cosmos SDK, and the consensus and networking layers, which are handled by the [Tendermint Core](https://tendermint.com/core/).

### What is the Tendermint Core?

The Tendermint Core is a blockchain application platform. Tendermint Core supports state machines in any language. The language-agnostic Tendermint Core helps developers securely and consistently replicate deterministic, finite state machines.

Tendermint BFT is maintained even when 1/3 of all machines fail by providing two components:

* A blockchain consensus engine
* A generic application interface


## Consensus in the Tendermint Core and Cosmos

The Tendermint Core is a high-performance, consistent, flexible, and secure **consensus module** with strict fork accountability. It relies on Deligated-Proof-of-Stake (DPoS) and Practical Byzantine Fault Tolerance (to recap these concepts in detail, [see here](ADD LINK TO CH2MOD2)).

Participants signal support for well-behaved, reliable nodes that create and confirm blocks. They do so by staking ATOM, or the native token of the respective chain. Staking bears the possibility of acquiring a share of the network transaction fees, but also the risk of reduced returns or even losses should the node become unreliable.

Network participants are incentivized to stake their ATOM with nodes which are the most likely to provide dependable service, and to withdraw their support should conditions change. A Cosmos blockchain is expected to adjust the validator configuration and continue even in adverse conditions.

Only the top 150 nodes by staked ATOM participate in the transaction finalization process as **validators**. The privilege of creating a block is awarded in proportion to the voting power a validator has. **Voting power** is calculated as *all the ATOM tokens staked by a validator **and** its delegates*. If a given validator's voting power is 15% of the total voting power of all validators, then the validator can expect to receive the block creation privileges 15% of the time.

Each new block is broadcast by the current block creator to the other validators, who are expected to respond promptly and correctly:

* Validators confirm valid candidate blocks.
* Validators absorb penalties for failing to do so.
* Validators can and must reject invalid blocks.
* Validators accept a block by returning their signature.

When sufficient signatures have been collected by the block creator, the block is finalized and broadcast to the wider network. There is no ambiguity in this process: either a block has the necessary signatures, or it does not. If it does, insufficient signatories exist to overturn the block and the block can be understood as **finalized** – there is no process by which the blockchain can be reorganized. This provides a level of absolute certainty when it comes to transaction finality that a probabilistic system like Proof-of-Work (PoW) cannot match.

Aggressive block times are feasible because the process is aimed at achieving high performance, and is based on dedicated validators with good network connectivity. This is quite different from PoW, which favors inclusion and must accommodate slower nodes with greater latency and less reliability. **A Cosmos blockchain can handle thousands of transactions per second with confirmations taking seven seconds**.

Even though validation is delegated to a subset of all network nodes, this process avoids the concentration of power. The community of users elects the validators by staking ATOM and participating in both the rewards and the risks of committing to providing a reliable, responsible block validation service.


## Upgradeability of chains

In any known blockchain, a change in the implementation requires an upgrade to the node software running on each node. In a disorderly process with voluntary participation, this can result in a hard fork – a situation in which one constituency forges ahead with the old rules and another adopts new rules. See [Chapter 3](ADD LINK HERE) for more detail on forking.

While this arrangement has positive aspects and proponents, it also has clear disadvantages in settings where **certainty** is a strict requirement. For example, uncertainty about transaction finality regardless of the degree of uncertainty may be unacceptable in settings that are concerned with authoritative registries and large assets.

In a Tendermint blockchain, transactions are irreversibly finalized upon block creation and upgrades are themselves governed by the block creation and validation process. This leaves no room for uncertainty: either the nodes agree to simultaneously upgrade their protocol, or the upgrade proposal fails. Hard forking is not an option.

Validators are the only nodes who vote on this decision. This means that delegators should be demanding when delegating as, unless they specify otherwise, by signaling their support with their stake they also lend their vote to the validator.


## Application Blockchain Interface (ABCI)

Tendermint BFT packages the networking and consensus layers of a blockchain and presents an interface to the application layer, the **Application Blockchain Interface (ABCI)**. Developers can focus on higher-order concerns while delegating peer-discovery, validator selection, staking, upgrades, and consensus to the Tendermint BFT. The consensus engine running in one process controls the state machine; the application runs in another process. **This architecture is equally appropriate for private or public blockchains**.

The Tendermint BFT engine is connected to the application by a **socket protocol**. ABCI provides a socket for applications written in other languages. When the application is written in the same language as the Tendermint implementation, the socket is not used.

![The application, ABCI, and Tendermint](/ABCI_3.png)

The Tendermint BFT provides security guarantees, including:

* **Forks** are never created, provided that half or more validators are honest.
* **Strict accountability** for fork creation allows determining liability.
* Transactions are **finalized** as soon as a block is created.

The Tendermint BFT is not concerned with the interpretation of transactions: that requirement occurs on the application layer. **Tendermint *agnostically* presents confirmed, well-formed transactions and blocks of transactions**. Tendermint is un-opinionated about the meaning any transactions have.

The *block time* is approximately seven seconds, and blocks may contain thousands of transactions. Transactions are finalized and cannot be overturned as soon as they appear in a block.


## Application-level concerns

There are at least two broad approaches to **application-level concerns** using blockchains:

1. Create an application-specific blockchain where everything that can be done is defined in the protocol.
2. Create a programmable state machine and push application concerns to a higher level, such as bytecode created by compilers interpreting higher-level languages.

Ethereum-like blockchains fall into the second category. Only the state machine is defined in the on-chain protocol, which defines the rules of contract creation, interaction, execution, and little else.

This method is not without its limitations:

* Very little is universally defined: standards for basic concerns (such as tokens) emerge organically through voluntary participation.
* Contracts can and do contain repetitive code that may or may not correctly implement the developer's intentions.
* The inherent flexibility makes it challenging to reason about what is correct, or even about what is friendly.
* There are practical limits to the complexity of operations, which are very low compared to what is possible in other settings.

These limitations make it especially difficult to perform analysis or reorganize data, and developers are forced to adapt to the constraints.

A **purpose-built or application-specific blockchain** is different. There is no need to present a "Turing-complete" language or a general-purpose, programmable state machine because application concerns are addressed by the protocol the developers create.

Developers who have worked with blockchains based on the Ethereum Virtual Machine (EVM) will recognize a shift in the way concerns are addressed. Authorization and access control, the layout of storage or the state, and application governance are not implemented as contracts on a state machine. They instead become properties of a unique blockchain that is built for a singular purpose.


## Further learning

You can find further information about the Tendermint Core in the [Tendermint Core documentation](https://docs.tendermint.com/master/#).

<HighlightBox type="info">

For a deeper dive on consensus and Tendermint visit:

* the [podcast on consensus systems](https://softwareengineeringdaily.com/2018/03/26/consensus-systems-with-ethan-buchman/) with Ethan Buchman
* the [Tendermint Core documentation on consensus](https://docs.tendermint.com/master/introduction/what-is-tendermint.html#consensus-overview)

</HighlightBox>


## Next up

The [next section](ADD LINK HERE) will introduce you to a variety of tools which developers work with in the Cosmos Ecosystem.
