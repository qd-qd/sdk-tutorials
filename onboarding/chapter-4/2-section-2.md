---
title: "Inter-Blockchain Communication"
order: 4
description: Introducing the IBC protocol
tag: deep-dive
---

# Inter-Blockchain Communication

Cross-chain communication in Cosmos enables parallelism and scalability with transaction finality. This transaction finality solves well-known problems that plague other platforms. This section explores the Inter-Blockchain Communication Protocol (IBC) that makes cross-chain communication possible.

<HighlightBox type="learning">

This section will cover:

* Independence and interoperability
* The Inter-Blockchain Communication Protocol (IBC)
* Hubs, zones, and the Cosmos Hub
* Connecting Cosmos chains with non-Tendermint chains
* The Gravity Bridge
* IBC features and components

</HighlightBox>

## Independence and interoperability

Most Cosmos applications execute on their own purpose-built blockchains running their own validator set. These are application-specific blockchains built with the Cosmos SDK.

However, applications on one chain may need to communicate with applications on another. For example, an application could accept tokens from another blockchain as a form of payment. Interoperability at this level calls for a method of exchanging data about the state and transactions on another blockchain.

While such bridges between blockchains can be built and do exist, they are generally constructed ad-hoc. By contrast, applications built with the Cosmos SDK have a common protocol and framework for implementing standardized inter-blockchain communication.

## The Inter-Blockchain Communication Protocol (IBC)

The [Inter-Blockchain Communication Protocol (IBC)](https://ibcprotocol.org/) is the basis for **interoperability** in Cosmos. It leverages Tendermint's instant finality to allow for the transfer of value (token transfers) and communication between heterogeneous chains. With IBC, blockchains with different applications and architecture specifications become interoperable whether or not they share a validator set.

Without IBC the interoperability of heterogeneous chains is difficult to achieve, because they may implement the consensus, networking, and application layers in different ways. As soon as a blockchain is compatible with IBC, it becomes interoperable with other blockchains.

### Modular design and application requirements

IBC allows building a wide range of cross-chain applications including token transfers, atomic swaps, multi-chain smart contracts (with or without mutually comprehensible virtual machines), and data and code sharding of various kinds. It is an end-to-end, connection-oriented, stateful protocol for reliable, ordered, and authenticated communication between heterogeneous blockchains arranged in an unknown and dynamic topology.

This is made possible by specifying a set of data structures, abstractions, and semantics that can be implemented by any distributed ledger, provided they satisfy a small set of requirements. Using IBC does not require in-depth knowledge of the low-level details of clients, connections, and proof verification. Applications that use the IBC protocol for cross-chain communication must be able to:

* Bind to one or more ports.
* Define packet data.
* Define optional acknowledgment structures and methods to encode and decode packet data.
* Implement the `IBCModule` interface.

IBC can be used to build a wide range of cross-chain applications, which include token transfers, atomic swaps, multi-chain smart contracts with or without mutually comprehensible virtual machines, and data and code sharding of various kinds.

## Hubs, zones, and the Cosmos Hub

Cosmos implements a **modular architecture with two blockchain classes**: **hubs** and **zones**.

**Zones** are heterogeneous blockchains carrying out the authentication of accounts and transactions, the creation and distribution of tokens, and the execution of changes to their respective chains.

**Hubs** are blockchains specifically designed to connect zones. Once a zone connects to a hub through an IBC connection, it gets automatic access to any other zones connected to that hub. This helps reduce the number of chain-to-chain connections that need to be established for interoperability. Data and value can be sent and received between such zones without the risk of double-spending tokens, for example.

There is no enforcement of an actual topology. A hub can be understood as a zone with many connections to other zones. Application zones can be expected to join the hubs in the ecosystem, but they are free to coalesce into any topology the developers find appropriate.

### The Cosmos Hub

The **[Cosmos Hub](https://hub.cosmos.network/main/hub-overview/overview.html)** was the first hub created. It is a public Proof-of-Stake (PoS) blockchain with a native token, ATOM.

The Cosmos Hub can be understood as a router facilitating transactions between the chains connected to it. For example, the Cosmos Hub allows transaction fees to be paid in different tokens, as long as the zone trusts the Cosmos Hub and the other zones connected to it.

## Connecting Cosmos chains with non-Tendermint chains

The IBC connection is not limited to Tendermint-based chains. Two types of non-Tendermint chains are supported:

* **Fast-finality chains:** any fast-finality consensus algorithm can establish a connection with Cosmos by adapting IBC to work with the non-Tendermint consensus mechanism.
* **Probabilistic-finality chains:** for non-Tendermint blockchains without fast-finality, like Proof-of-Work (PoW) chains, a simple adaptation of IBC is not sufficient. A special kind of proxy chain called a **peg-zone** helps establish interoperability in these cases.

### Peg-zones

Peg-zones are fast-finality blockchains, which track the state of another blockchain to establish its finality. The peg-zone chain has fast finality and is therefore IBC-compatible; its role is to establish finality for the probabilistic-finality blockchain you seek to connect with by providing a **bridge** between the rest of the IBC network's chains and the target chain.

An example of a peg-zone implementation exists for Ethereum and is named the **[Gravity Bridge](https://github.com/cosmos/gravity-bridge)**.

## The Gravity Bridge

The Cosmos Gravity Bridge is designed to run on the Cosmos Hub. It focuses on maximum design simplicity and efficiency. The bridge can transfer ERC-20 assets originating on Ethereum to Cosmos-based chains and back to Ethereum. Transactions are batched with transfers netted out. This creates efficiency at scale and lowers the transaction cost for each transfer.

The Gravity Bridge consists of several components:

* **`Gravity.sol`:** an Ethereum smart contract on the Ethereum blockchain.
* **Cosmos Gravity module:** a Cosmos module designed to run on the Cosmos Hub.
* **Orchestrator:** a program that runs on Cosmos validators monitoring the Ethereum chain and submitting events that occur on Ethereum to Cosmos as messages.
* **Relayers:** a network of nodes that compete for the opportunity to earn fees for sending transactions on behalf of the Cosmos validators.

### How it works

Tokens are locked on the Ethereum side by sending them to the `Gravity.sol` smart contract. This emits an event that is observable to validators running Orchestrator.

When a quorum of validators agrees that tokens have been locked on Ethereum, including the requisite confirmation blocks, a relayer is selected to send an instruction to the Cosmos Gravity module, which issues new tokens. This is non-dilutive: it does not increase the circulating support because an equal number of tokens is locked on the Ethereum side.

To transfer tokens from the Cosmos Hub to the Ethereum blockchain, tokens on the Cosmos network are destroyed and an equal number are released from the `Gravity.sol` smart contract - where they were previously deposited.

### Key design components: trust in integrity

If a Cosmos chain is trustworthy, you can trust the Gravity Bridge operated by it as long as it performs within certain parameters.

Bridges to Cosmos chains derive their trustworthiness from the degree of trust associated with the Cosmos chain to which they bridge. Peg-zone validators must maintain a trusted Ethereum node. This removes all trust and game theory issues that usually arise when involving independent relayers, dramatically simplifying the design.

The signing of fraudulent validator set updates and transaction batches meant for the Ethereum smart contract is punished on the Cosmos chain by **slashing** – this refers to a financial penalty, specifically the removal of staked value from the validator.

Verifying the votes of the validator set is the most expensive on-chain operation Gravity has to perform. Existing bridges incur more than double the gas costs for signature sets as small as eight signers.

### Operational parameters ensuring security

The bridge requires a validator set update on the Ethereum smart contract at least once every Cosmos unbonding period, usually every two weeks. Without an update every unbonding period, the validator set stored by the Ethereum smart contract could contain fraudulent or malicious validators who cannot be slashed for misbehavior.

Cosmos full nodes do not verify events coming from Ethereum, as events are validated into the Cosmos chain's state based purely on the signatures of the current validator set. If validators represent more than 2/3 of the stake, an event could be added to the state even without a corresponding event on Ethereum. In this case, observers of both the Cosmos and Ethereum chains will need to "raise the alarm" on the issue. This functionality is built into relayers.

## IBC tools, features, and components

IBC functionality relies on a variety of elements including:

* Clients
* Connections
* Channels
* Relayers, proofs, and paths
* Dynamic capabilities
* Handshakes
* Receipts and timeouts
* Acknowledgements

Briefly reviewing each of these is beneficial.

### Clients

IBC clients **track the consensus state** of other blockchains and the proof specs required to properly verify proofs against the client's consensus state. They are **light clients**, meaning that they interact with blockchains without storing the complete ledger themselves. A client can be associated with any number of connections to the counterparty chain.

Supported IBC clients are:

* **Solomachine light clients:** devices such as phones, browsers, or laptops.
* **Tendermint light clients:** the default for Cosmos SDK-based chains.
* **Localhost (loopback) clients:** useful for testing, simulation, and relaying packets to modules on the same application.

### Connections

Connections are responsible for **facilitating all cross-chain verification** of the IBC state. A connection can be associated with any number of channels.

A connection enables the communication between two separate blockchains through clients associated with each chain. A connection handshake is responsible for verifying that the light clients on each chain are the correct ones for their respective counterparties.

### Channels

Channels can be established between two IBC ports. Each port is exclusively owned by a single module. IBC data packets are sent over channels to allow modules to communicate with one another.

Port channels allow IBC to correctly route the packets to the destination module, while also allowing modules receiving packets to know where the packet came from. Modules may choose which channels they wish to communicate over. IBC expects modules to implement callbacks called during the channel handshake.

Channels can be categorized as **ordered** or **unordered**, depending on whether or not it is important for data packets to be received in the same order they were sent.

### Relayers, proofs, and paths

In IBC, blockchains do not directly pass messages to each other over the network. To communicate, blockchains commit their state to a precisely defined **path** which is reserved for a specific message type and a specific counterparty.

**Relayers** monitor for updates on these paths and relay messages by submitting the data stored under the path, along with **proof** of that data to the counterparty chain.

### Dynamic capabilities

IBC is intended to work in execution environments where modules do not necessarily trust each other. IBC needs to authenticate module actions on ports and channels. Only modules with the appropriate permissions can use channels.

A self-contained module on one blockchain can communicate with modules on other blockchains by sending, receiving, and acknowledging packets using ports and channels that are uniquely identified. Upon binding to a port or creating a channel for a module, IBC returns a **dynamic capability** that the module must claim to use that port or channel. This binding strategy prevents other modules from using that port or channel since those modules do not own the appropriate capability.

### Handshakes

**Handshakes** are used to open channels, creating a secure line of communication between two different blockchains. A four-step handshake takes place in the following way:

1. Chain A sends a message to signal a channel initialization attempt with chain B.
2. Chain B sends a message to try opening the channel on chain A.
3. Chain A sends a message to mark chain A's channel end status as "open".
4. Chain B sends a message to mark chain B's channel end status as "open".

With both channel ends "open" communication can proceed.

Just as ports come with dynamic capabilities, channel initialization returns a dynamic capability the module must claim so that modules can pass in a capability to authenticate channel actions, for example, to send packets. Channel capability is passed into the callback in the first part of the handshake.

### Messages

Messages are one of two primary objects handled by a module in the Cosmos SDK. The other primary object handled by modules is queries. While messages inform the state and have the potential to alter it, queries inspect the module state and are always read-only.

In the Cosmos SDK, a **transaction** contains **one or more messages**. The module processes the messages after the transaction is included in a block by the consensus layer.

### Queries

A query is a request for information made by end-users of an application through an interface and processed by a full node. Available information includes:

* Information about the network
* Information about the application
* Information about the application's state

Queries do not require consensus to be processed as they do not trigger state transitions. Therefore, queries can be fully handled independently by a full node.

### Receipts and timeouts

IBC works over a distributed network, which may force reliance on potentially faulty relayers to relay messages between ledgers. Cross-chain communication also requires handling instances where a packet does not get sent to its destination on time, or at all.

A proof-of-packet **timeout** can be submitted to the original chain when a timeout is reached, which can then perform application-specific logic to timeout the packet by rolling back any changes triggered by the packet sent and refunding senders any locked funds.

*Unordered channels* can receive packets differently from the original sending sequence, but the timeout of a single packet in an *ordered* channel will close that channel. IBC writes a packet **receipt** for each sequence it has received in an unordered channel.

### Acknowledgments

Modules also write application-specific **acknowledgments** when processing a packet. This can be performed in two ways:

* **Synchronously**, if the module processes packets as soon as they are received from an IBC module.
* **Asynchronously**, if the module processes packets at some later point.

This acknowledgment data is opaque to IBC, similar to the packet data. Receiver modules have to encode acknowledgments so that sender modules can decode them correctly.

After the acknowledgment has been written by the receiving chain, a relayer sends the acknowledgment back to the original sender module, which then executes its application-specific acknowledgment logic based on this response.

When the acknowledgment is received successfully on the original sender chain, the IBC module deletes the corresponding packet commitment, as it is no longer needed.

## Further learning

<HighlightBox type="reading">

* For more detailed information on hubs and zones on the mainnet and in the testnet, check out this [map of zones](https://mapofzones.com/).
* 
* 
* 

</HighlightBox>

## Next up

In the [next section](ADD LINK HERE), you will move away from the technical features of Cosmos to look at several hypothetical use cases that highlight the expanded potential for blockchains platformed on the Cosmos Ecosystem.
