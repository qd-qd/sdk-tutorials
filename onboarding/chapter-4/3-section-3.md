---
title: "The Cosmos SDK and other ecosystem tools"
order: 2
description: Introducing the tools for developing Cosmos application blockchains
tag: deep-dive
---

# The Cosmos SDK and other ecosystem tools

A foundational principle of Cosmos is that the development of blockchain solutions become as convenient and accessible as possible. To this end, a variety of tools is available to developers, first and foremost the Cosmos SDK.

<HighlightBox type="Learning"> 

This section will cover:

* The Cosmos SDK: Modular and Customizable design
* Alternative blockchain frameworks and SDKs
* Using the Cosmos SDK
* CosmJS: 
* CosmWasm: Multi-chain smart contracts
* Starport: building application-specific blockchains with one command
* Atlas
* ATOM

</HighlightBox>


## The Cosmos SDK: Modular and Customizable design

The Cosmos network focuses on an ecosystem for easy blockchain development that provides customizability and interoperability, establishing a stable universe determined by the same rules that apply to the whole ecosystem equally. _Click on the hotspots in the image to learn more about the main goals of the Cosmos network._

<H5PComponent :contents="['/h5p/M1-ecosystem-constellation-HS']"></H5PComponent>

The Cosmos SDK is a generalized framework to build secure blockchain applications on the Tendermint BFT in Golang. It is a modular framework for application-specific blockchains. The design is based on two major principles: **modularity** and **capability-based security**. The Cosmos SDK was envisioned to be an npm-like framework for secure applications on top of Tendermint. Over time it has become an advanced framework for custom application-specific blockchains.

The ready-built modules of the Cosmos SDK are easy to import, adapt, and use. Developers can create their own modules to introduce specific functionalities. With the growth of the ecosystem, the number of modules will grow, facilitating the development of more complex applications.

<HighlightBox type="tip">

*Building on modular components, many of which you did not write yourself* – does this increase the potential for attacks, and faulty or malicious nodes operating undetected? No need to worry.

The Cosmos SDK is built on the [object-capability model](https://docs.cosmos.network/main/core/ocap.html). It not only favors modularity but also encapsulates code implementation. An object-capability model ensures that:

* There is no way for objects in the memory to be discovered just by going through the composed objects of others.
* The only way to have references to objects or to access services is to have been passed the relevant object references.

</HighlightBox>

<HighlightBox type="info">

The default consensus mechanism available when developing with the SDK is the [Tendermint Core](https://docs.tendermint.com/master/).

</HighlightBox>


## Alternative blockchain frameworks and SDKs

As the Cosmos SDK is modular, developers can port existing codebases in Go on top of the SDK. This allows developers to build on Cosmos without having to compromise too much on the toolset and environment used.

For example, with [Ethermint](https://github.com/tharsis/ethermint) developers can use the Ethereum Virtual Machine (EVM) from the main Go Ethereum client as a Cosmos SDK module, which is compatible and combinable with existing modules.

<HighlightBox type="info">

Ethermint is a software developed to port the EVM into a Cosmos module. It makes scalable, high-throughput, PoS blockchains possible. These are fully compatible with Ethereum and the Cosmos SDK.

Ethermint is Web3 compatible and achieves high throughput with Tendermint and horizontal scaling with IBC. It provides a Web3, JSON-RPC layer to interact with Ethereum clients and tooling.

</HighlightBox>

All Ethereum tools, such as Truffle and Metamask, are compatible with Ethermint. Developers can even port their Solidity smart contracts to interact with the Cosmos ecosystem. Building a chain is not necessary to develop Cosmos-compatible smart contracts, it can be all done with Ethermint. While Ethermint allows running vanilla Ethereum as a Cosmos application-specific blockchain, developers benefit from the Tendermint BFT.


## Using the Cosmos SDK

Developers create the application layer using the **Cosmos SDK**. The Cosmos SDK provides:

<Accordion :items="
    [
        {
            title: 'A scaffold to get started',
            description: 'The Cosmos SDK provides a head start and a framework for application development.'
        },
        {
            title: 'A rich set of modules',
            description: 'The Cosmos SDK provides a rich set of modules that address common concerns, such as governance, tokens, other standards, and interactions with other blockchains through the Inter-Blockchain Communication Protocol (IBC).'
        }
    ]
"/>

The creation of an application-specific blockchain with the Cosmos SDK is largely a process of selecting, configuring, and integrating well-solved modules, also known as "composing modules". This greatly reduces the scope of original development required, as development is mostly focused on the truly novel aspects of each particular application.

<HighlightBox type="info">

The Inter-Blockchain Communication Protocol (IBC) is a common framework for exchanging information between blockchains. You will learn more about IBC in the [next section](ADD LINK HERE). For now, it is enough to know that it exists and it enables seamless interaction between blockchains that want to transfer value (token transfers) and exchange information. It enables communication between applications that run on separate application-specific blockchains.

</HighlightBox>

The application, consensus, and network layers are contained within the custom blockchain node that forms the foundation of the custom blockchain.

Tendermint passes confirmed transactions to the application layer through the **Application Blockchain Interface** (ABCI). The application layer must implement ABCI, which is a socket protocol. Tendermint is unconcerned with the interpretation of transactions and the application layer can be unconcerned with propagation, broadcast, confirmation, network formation, and other lower-level concerns that Tendermint attends to, unless it wants to inspect such properties.

Since the ABCI is a socket protocol, developers are free to create blockchains in any language that supports sockets, provided their application implements ABCI. ABCI defines the boundary between replication concerns and the application, which is a state machine.

This is itself a considerable step forward that simplifies the creation of unique blockchains.


## Cosmos tools

In addition to the Cosmos SDK itself, there are a variety of related tools for the developer to make use of.

### CosmJS

**CosmJS** is a JavaScript library for the Cosmos SDK, and is used for writing front-end applications and servers that interact with a blockchain. It is a [powerful tool](https://github.com/cosmos/cosmjs/wiki/What-can-CosmJS-do-for-me%3F), which can be used to create wallets, explorers, IBC relayers, and other decentralized applications (dApps). It is written in TypeScript and can therefore be client or server side.

### CosmWasm: Multi-chain smart contracts

[CosmWasm](https://cosmwasm.com/) is a multi-chain platform to build robust dApps for Cosmos using smart contracts. It adds further flexibility for developers and makes smart contract development faster. Its key features are:

* Mature tools for the development and testing of smart contracts.
* Close integration with the Cosmos SDK and ecosystem.
* A secure architecture to avoid attack vectors.

With CosmWasm, smart contracts can run on multiple chains with the help of the Inter-Blockchain protocol (IBC). It is written as a module to be plugged into the Cosmos SDK, and leverages the speed of Wasm and the power of Rust through an actor-model design focused on providing a library.

<ExpansionPanel title="The actor model">

The actor model is a design pattern for reliable, distributed systems, and the pattern underlying CosmWasm smart contracts. Each actor has access to its own internal state and can only message other actors through a "dispatcher", which maintains the state and maps addresses to code and storage.

</ExpansionPanel>

CosmWasm's design makes the code agnostic to the details of underlying chains. It only requires a Cosmos SDK application to embed the `Wasm` module. It is adaptable to different development environments and makes it possible to connect chains. 

It is a solid platform to develop on because:

* If you want to change chains, you can easily transfer smart contracts and decentralized applications (dApps).
* If your application grows, you can launch your chain for the next version of your smart contract. You do not need to compile and deploy the binaries again.

### Starport: building application-specific blockchains with one command

[Starport](https://cosmos.network/starport/) is a developer-friendly, command-line interface (CLI) tool for application-specific blockchains building on Tendermint and the Cosmos SDK. 

The CLI tool offers everything developers need to build, test, and launch a chain. It accelerates development by scaffolding and assembling all components needed for a production-ready blockchain. Starport lets you build a blockchain in minutes, making the process from initial idea to production 95% faster. This lets developers focus more strongly on the business logic of their application.

With Starport, developers can:

* Create a modular blockchain written in Go with a single command.
* Start a development server, to experiment with token creation and allocation as well as module configuration.
* Allow for inter-chain token transfers by using its built-in IBC relayer to send value and data to different chains.
* Benefit from a fast-developed frontend with automatically generated APIs and web pages in JavaScript, TypeScript, and Vue.

When you scaffold with Starport, things like key management, creating validators, and transferring tokens can be done through the CLI.

### Atlas: Cosmos SDK module registry and node explorer

[Atlas](https://atlas.cosmos.network/) implements a registry for modules. Developers can publish, update, and download Cosmos SDK modules with Atlas. It is a helpful tool for those who wish to get an overview of existing modules when developing their applications.

Atlas also offers a [node explorer](https://atlas.cosmos.network/nodes) that lets you crawl through the nodes of a Tendermint-based network to discover its topology and the nodes' metadata.



## Further learning

* ???


## Next up

In the [next section](ADD LINK HERE), you will take a closer look at arguably the Cosmos ecosystem's most valuable feature: the **Inter-Blockchain Communication protocol**, or **IBC**.

