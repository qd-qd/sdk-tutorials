---
title: "Cosmos-based Use Cases"
order: 5
description: An introduction to projects in the Cosmos ecosystem
tag: deep-dive
---

# Cosmos-based Use Cases

In this course you have looked at the features of blockchain in general and of Cosmos in particular. This included an exploration of [a range of use cases](ADD LINK TO CH1/MOD5 HERE) for this technology beyond the cryptocurrencies and NFTs which brought blockchain to global attention.

Now it's time to bring that same focus more closely onto what Cosmos can allow developers to achieve: creating applications which previous blockchain platforms would have proved too limiting for them to truly flourish.

<HighlightBox type="Learning">

This section will cover:

* Cosmos – a use case overview
* Use case 1: A FinTech application
* Use case 2: A decentralized marketplace for data
* Use case 3: A decentralized platform for independent artists

</HighlightBox>


## Cosmos – a use case overview

To reiterate a definition: *Cosmos provides an environment in which different blockchain-based projects can coexist and even communicate with each other, each one free to reside on its own custom-defined chain*. This provides some valuable advantages over previous platforms for decentralized apps:

* **Flexibility and ease of use**: developers are provided with a software development kit, the Cosmos SDK, which provides a suite of modular resources that shortcut the need to build many universally necessary features from the ground up.
* **Sovereignty**: developers can define the rules of their chains independent of many outside factors, and once in operation the governance of each blockchain is in the hands of its users, without the need to worry about platform-level governance impacting applications.
* **Interoperability**: the native Inter-Blockchain Communications protocol (IBC) makes communications and transactions between dApps in Cosmos a straightforward and stable feature of the environment, and even supports interoperability outside of the ecosystem.
* **Speed**: each blockchain only hosts the applications its developer wants it to, so network resources aren't divided between all dApps in the ecosystem. Reliable coding from Cosmos SDK modules, combined with dedicated on-chain resources, means efficiency and speed.

The question is, what can be achieved as a result?

### A universe of possible use cases

The potential use cases for interoperable dApps are incredibly wide-ranging, from establishing **resilient, autonomous organizations** that empower communities (allowing them to organize and allocate resources to members, vote on impactful governance decisions, etc.) to **Decentralized Finance** (DeFi) applications that can allow anyone around the world to buy, trade, invest, and lend – even those without a bank account.

**Fintech**, a term derived from "financial technology", refers to software, mobile apps, and other technologies aimed at improving and automating traditional forms of finance for both businesses and consumers. Examples include decentralized exchanges, open marketplaces, commercial token economics, and gaming economies, to name just a few.

<ExpansionPanel title="Decentralized exchanges (DEXs)">

A decentralized exchange is a peer-to-peer cryptocurrency marketplace, where transactions between traders take place directly, often facilitated through the use of smart contracts.

The values of cryptocurrencies, like most things, are typically assessed in terms of their dollar equivalent, and the difficulty of blockchains interacting with each other has meant that trading one cryptocurrency for another typically requires converting an investment from crypto to fiat to crypto again, forcing users in and out of the centralized money markets. 

When independent blockchains are able to transact directly, the unmediated exchange of their value tokens becomes a viable prospect. DEXs deliver one of blockchain's great decentralization potentials: allowing individuals to interact without the necessity of handing over management of their funds to banks, brokers, or any other custodian or intermediary agent.

</ExpansionPanel>

<ExpansionPanel title="Open marketplaces">

Similar in concept to DEXs, the decentralization of marketplaces allows investors focused on traditional market trading to deal with each other directly, instead of relying on centralized stock exchanges (be they in real-world locations, like the New York or Shanghai Stock Exchange, or entirely online, like the Nasdaq). 

Exchanges may impose qualification criteria on companies before they can be listed, limiting opportunities both for those seeking investment and those looking for projects to support. In addition, the exclusivity and inaccessibility of market trading as an activity prohibits many ordinary people from even considering the possibility of investment as a way to grow their own wealth.

A decentralized marketplace could allow investors and businesses of all scales to find each other without hindrance from the established ways of doing things, enjoying very low fees and instant transaction confirmation.

</ExpansionPanel>

<ExpansionPanel title="Commercial token economics">

Token economics, or "tokenomics", is a way of grounding extrinsic value in a digital token-based system. Whereas a cryptocurrency is treated as a commodity in itself, token economics allows the same kind of transactional system to be put to use in relation to content creation and commercialization. An example might be monetizing streaming services for music or video, which in turn could help to decentralize content production by funneling more revenues directly to content creators rather than to the media platforms.

Tokens could also be used to reward fan engagement or through community-driven incentives. Community is a big part of fandom, and the nature of blockchain brings certain basic benefits (trustworthy interactions and exchanges, sources of information, data security) that can be usefully integrated into a creator's interactions with their fan-base. The adoption of tokens could allow individual fans to support creatives in a tangible way by "investing" in them, while also directly benefiting from value accruing in the tokens they own.

</ExpansionPanel>

<ExpansionPanel title="Game economies">

Gaming is a vastly lucrative industry on a number of levels. Revenues that were once entirely generated by unit sales of the game itself are now dwarfed by micro-transactions and in-game purchases to such an extent that many titles are offered as free-to-play in terms of up-front costs to the user. Sub-industries that see players earn "salaries" for their time investment have become very well established, as are marketplaces for in-game assets such as high level ready-to-play characters, or rare equipment and other valuable "loot".

All these potential revenue streams could find a basis in blockchain-based systems. However, the interoperability that Cosmos provides could take things to the next level, with value able to flow between different games, gaming systems, or simply into the real world.

</ExpansionPanel>

The rest of this section will look at three hypothetical use cases


<!--SEPARATOR IMAGE WOULD BE GOOD-->

## Use case 1: A FinTech application

A **decentralized exchange** project could made possible by relying on all the advantages of Cosmos and its SDK: transaction finality, fast transaction processing (and therefore high throughput), high scalability, a high degree of security (based on the security provided by the whole Cosmos ecosystem), and the possibility of small fees, while also connecting to other chains for cross-chain token transfers.

### Project definition

* A DEX dApp built on a Cosmos SDK chain.

### Aims

* Permits simple trades with genuine ease of use.
* Helps new blockchain adopters and users conduct independent trading.
* Lower entry costs and no technical barriers to entry.

### Blockchain characteristics

* A public chain built with Cosmos SDK, allowing creating an easy-to-develop-on protocol layer as infrastructure.
* Tendermint consensus, providing PoS consensus.
* Smart contract execution and native tokens, used for fees, block rewards for validators, gas for transfers, and the delegation of stakes to validators.
* Could either be connected to the Cosmos Hub or serve as a Hub for other Zones:
  * As a Hub, permits building apps on the DEX.
  * The DEX then becomes the starting point for a decentralized finance ecosystem.
* Bridges to other chains like Ethereum and Bitcoin.
* Standards for tokens, similar to the ERC standards.
  * Could also be made compatible with existing standards.

### Potential dApps

A public chain provides an environment for dApps based on smart contracts and storing digital assets. dApps to be built on the chain include:

* A wallet for users to connect to the DEX and use the services provided.
* An application for staking.
* A build explorer for the main chain and all side-chains
* An environment to create token projects like NFTs and offer them to DEX users (providing the project with a liquidity market).
* Bridges to other chains, for safe and fast asset swaps with other chains.
* Features like automated market making which combine trading, market predictions, and liquidity mining.


<!--SEPARATOR IMAGE WOULD BE GOOD-->

## Use case 2: A decentralized marketplace for data

The generation and consumption of data has become a vast and valuable global industry in the internet era, but the relationship is often perceived as unequal, with system participants who generate this data resource not able to share in the profits derived from their activity. 

The value of data is determined based on how it can be connected, applied, and used. A system which protected subject anonymity while monetizing this data at the source could break down public aversion or apathy towards "big data" by sharing the wealth more fairly.

### Project definition

* An incentivized marketplace for sharing the value of data

### Aims

* Avoids collection and use of data by data consumers without paying for access
* Monetizes data sharing to reward data providers

### Legacy factors

* Traditional data systems present issues with data gathering and analysis: 
  * Rely on large centralized databases that are expensive to set up and manage.
  * Forgery and falsification are difficult to detect, because verification and recovery is difficult.

### Blockchain characteristics

* Public chain that connects companies that collect and generate data with those that need to buy it to develop their business. Blockchain technology provides data storage **and** serves as a marketplace.
* Business model: **Data providers** gather and push data to the chain, and are rewarded with native tokens depending on the value of the data itself. **Data consumers** can then buy access with the native token and analyze the data to drive their service or business.
* Main chain serves as a **hub** for certification and verification of data pushed to the chain, and as a central place to allocate the token transfers between data providers and buyers.
* **Zones** are databases for the different data types connected to the hub.
* Data is sourced from user activity related to IoT, sports, healthcare, logistics, etc.
* **Storage advantages**:
  * Distributed database, with same security for each node connected to the chain.
  * Forgery and falsification of data are easily detected due to immutability.
  * Recovery and verification can both be facilitated in a blockchain infrastructure (role of validators is very important).
* **Marketplace advantages**:
  * Sensitive data (personal health, commercial activity, etc.) can be anonymized to increase privacy and encrypted for data integrity.

### Potential dApps

Applications to be built on top of the chain could include:
* Wallet for data providers and consumers.
* Data gathering methods (for example: connecting a data-gathering IoT device to the blockchain ecosystem with provided certificates).
* Certificate management.


<!--SEPARATOR IMAGE WOULD BE GOOD-->

## Use case 3: Decentralized platform for independent artists

Due to legacies and complex mechanisms in art markets, cultural creators like musicians and visual artists often do not benefit appropriately from the revenue streams generated by their art. Value accrues post-sale in highly centralized, exclusionary social spheres that form barriers between creators and the wealth derived from their work.

### Project definition

* A value-sharing platform for artists, distributors, and consumers.

### Aims

* Bring artists and art consumers closer together.
* Give artists a bigger portion of the revenue they create.
* Make artists more independent from publishers and streaming platforms.
* Open up new liquidity markets for artists to acquire funding for projects.

### Blockchain characteristics

* A public chain built on Cosmos SDK that connects artists to fans:
  * A main chain hub handles all transactions between artists and users.
  * Zones are specific to particular artists or art providers (uploading artwork metadata, issuing tokens for investors, etc.).
* Native tokens are issued for block creation, paying fees, and transactions between artists and consumers (transparent fee and revenue distribution in real-time).
* Works of art are tracked through their metadata using the blockchain’s typical hash tree structure. Every time a user accesses or consumes the art, the chain adds an entry to its ledger to track how much the product is in demand.
* Based on this user activity, artists receive payments (such as royalties) directly and automatically.
* Settings could allow artists to delegate their stakes, to let earnings continue to grow and at the same time strengthen the security of the network
* Tokens could be issued with which fans can support artists, by “investing” in that artist through token sales instead of acquiring artwork.
* Fans could receive a unique digital asset as a “reward”, literal tokens of appreciation for their investment.

### Potential dApps

Allows for dApps that build on the chain:
* Wallet for payments.
* Application to download metadata and access the artwork (for example, a music player that converts metadata to songs).
* Explorer for the chain.
* Issuance of tokens to pool resources.


## Further learning

The hypothetical project descriptions in the section are informed by existing projects in the Cosmos ecosystem. To learn more about such projects, check the following links:

* Use case 1: [Eco.com](https://eco.com/) is an example of a Fintech application.
* Use case 2: [DATA](https://data.eco/), or the "Decentralized AI-powered Trust Alliance", is an example of a decentralized data marketplace.
* Use case 2: [AMO](https://www.amo.foundation/) provides services based on gathering vehicle and driver data.
* Use case 3: [BitSong](https://bitsong.io/) is a multifunctional blockchain-based ecosystem built to empower the music industry. You can read more about it [here](https://docs.bitsong.io/).
* Use case 3: [Crowd Control](https://crowdcontrol.network/#/) is an example of a community-driven online card game system.
* See here for [an overview of existing projects on Cosmos](https://v1.cosmos.network/ecosystem/apps). 


## Next up

In the [final section of the course](ADD LINK HERE), you can get a practical feel for Cosmos by using a wallet to buy and stake ATOM with a validator, engaging with the Cosmos ecosystem directly.
