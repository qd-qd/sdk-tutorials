---
title: "Network and Protocols"
order: 2
description: 
tag: deep-dive
---

# Networks and Protocols

xxxxxINTRO-PARAxxxxxx

<HighlightBox type="learning">

This section will cover:

* Data Transfer
* Networking and protocols
* Points of failure in networks
* Peer-to-peer (P2P) networking
* Blockchain as a merging of data storage and network

</HighlightBox>


## Introduction

A few network concepts are relevant to understanding blockchain technology. Networks are connected through communication channels between the different nodes or data links, allowing them to exchange data and share resources, operating programs, and information.

Here you will explore the concept of data transfers, and how protocols in networking can solve problems in a hierarchy-free, fault-prone environment when it comes to network failures.

You can also check this chapter's [Resource Bank](ADD LINK HERE) for some useful networking vocabulary.

![A network of computers](images/network.png)


## Data transfer

The most basic attribute of a network is the ability to transfer data between computers. How does that process work? 

Imagine two computers that are connected and have access to two different databases:

1. Computer A sends a request for a set of information that is located on another computer.
2. Computer B accesses its database, querying for the data Computer A asked for.
3. Computer B retrieves the data and compiles a document.
4. Computer B sends the document to Computer A.
5. Computer A receives the document and interprets the data, perhaps storing it in its database or executing a series of actions.

In general, an encode-decode sequence happens on the two computers to **synchronize data between machines**. First, a sequence of characters is *encoded* in a specialized format, then it is sent, and finally it is *decoded* by reversing the process.

<HighlightBox type="info">

Common codes include the American Standard Code for Information (ASCII) for text files, Unicode, MIME, BinHex, and Uuencode, and (in the context of data communications among others) Manchester encoding.

</HighlightBox>

An **API request** is an ideal example of such a document transfer.

### Application Programming Interfaces and API Requests

The term **application programming interface (API)** describes _a connection between computers (and their software)_. You may hear the word API, or more specifically *web API*, quite often when it comes to communication between computers via the internet. You can find APIs for software libraries and programming languages. 

With APIs, developers can make calls or *requests* to send and receive information, hence the term **API request**. Such types of communication are often done using **JSON**, a programming language.

<HighlightBox type="info">

**JSON** is an open-standard, language-independent **data format**. It is a publicly-available standard for encoding information that is stored in a file, and is not limited to one programming language. It provides a data format for browser-server communication, and uses human-readable text to transmit data objects.

JSON is based on JavaScript. It was developed as a response to the need for a protocol that could ensure server-to-browser communication without relying on browser plugins like Java or Adobe Flash Player (i.e. software components which add new features to web browsers and are also referred to as "add-ons" or "extensions").

Other formats comparable to JSON  are XML, CSV, and YAML.

</HighlightBox>

What are potential failures of an API request?

* The client could send a request that the server does not understand, or send a malformed request.
* The server could create a document that the client does not understand, for example, a server sends XML when the client expects JSON.
* The server could send a malformed document.
* Either party could send a malicious request, for example, an SQL injection (a technique used to insert code into a database which could undermine or destroy it).

In modern network systems (and, in fact, in the web itself) a great deal of effort goes into mitigating translation and synchronization issues between clients and servers. Traditionally, network synchronization issues were often mitigated by implementing some kind of hierarchy. 

Blockchain uses a **non-hierarchical approach** to mitigate synchronization issues by making sure that every participant always has access to enough data to verify the integrity of ALL the data in the network.

Before diving into how these issues are approached with blockchain technology, revisit how protocols in networking solve problems inherent to a hierarchy-free, fault-prone environment.


## Networking and protocols

The term **networking** covers both _hardware and the software protocols used to transmit data and let computers communicate_. The interaction between software and hardware becomes especially interesting in a blockchain context because of a network's physical aspect.

Imagine a cable connection between two computers. Traditionally a coaxial cable was used to carry a signal. Cables can be subject to interference from many things, so there is no guarantee that the signal originating at point A will be received by point B.

To mitigate this problem and ensure smooth communication, a whole stack of hardware and software protocols has been developed. Remember, **protocols** are like behavior guidelines for machines that help them cooperate and understand each other, as well as mitigate any translation and synchronization issues.

As an example, think about what happens in **the case of missing data**.

![TCP request](images/tcp-request.png)

To facilitate data transfer, protocols like TCP split data into small packets and transmit each one individually. These bits of data are converted into an analog signal on the hardware level. On the receiving end, the signals are reconstructed and the software protocol re-assembles the original piece of data. If a packet is missing, the receiving computer can ask for **re-transmission** of the missing bundle of data.


## Points of failure in networks

The function of a network is largely defined by its **degree of centralization**. Generally, networks can be centralized, decentralized, or distributed. You will see the term _decentralized_ come up a lot in blockchain literature. 

What exactly constitutes a distributed vs. decentralized system is a hotly debated subject. Various network typologies have been proposed. Some view resource and power control as important aspects to differentiate networks. Differentiating distributed and decentralized networks by the location and control of resources includes a linear spectrum notion of centralization in networks. 

For the purpose of this discussion, take the main difference between the different types of network to be the number of **points of failure**.

A **point of failure** can be understood as _a node or a part of a network whose failure leads to the shutdown or dysfunction of the entire network, or to the system no longer being able to perform its intended operations_. Centralized networks have **one** point of failure, which means they can be compromised by activity at that single point. Decentralized networks can tolerate multiple simultaneous failures before suffering the same extent of compromise.

<ExpansionPanel title="Fault tolerance">

**Fault tolerance** is _the capability of a computer, electronic system, or network to keep operating even when components fail_.

A **fault-tolerant design** requires:

* **No single point of failure**, as a fault-tolerant system should continue operating uninterrupted while it is repaired.
* **Fault isolation and containment**, as failures should not affect the entire system by being isolated and contained.
* **Reversion modes** should be available.

When learning about blockchain, it is worth understanding these fundamentals because the technology operates in a similarly uncertain environment. Blockchain is designed to be fault-tolerant, thereby minimizing potential disruption and damage in adverse conditions.

</ExpansionPanel>

Although the advantages and disadvantages of each network type continue to be debated, to conclude: network design has implications on functionality and more general issues, for example privacy and transparency. A network does not have to be purely centralized, decentralized, or distributed – it can incorporate different components of each type. The design should always match the envisioned functionality of the network.


## Peer-to-peer (P2P) networking

A **peer-to-peer (P2P) network** has a **distributed architecture**, meaning that work is distributed among members of the network. P2P networks are usually composed of computer systems as peers and connect via the internet. Each participant, called a node, connects to a limited number of other nodes, which are commonly referred to as its **peers**. Peers make resources like computing power and network bandwidth available to all peers in the network.

All participants are equal in that they can all request information and answer requests. Understood as equality is that all participants are **equally privileged and equipotent**. For this reason, P2P networking has been seen as a means for an egalitarian social network.

P2P networks are very different from client-server networks, in which data supplier and data consumer roles are ascribed to different entities and all communication happens through a central server.

In a traditional client-server architecture, participants are either a client, which requests information, or a server, which answers those requests – the API request is a classic client-server example. Centralized security databases that restrict control to server assets help improve security. Client-server networks are suitable for large networks but can become expensive when handling large amounts of data, transfers, and clients.

![Client-server model](images/client-server.png) 

In P2P networking there is no central server, storage, or authentication of users. Peers can be understood as file servers and clients at the same time. If a node cannot answer a request, it will forward it to some or all of its known peers.

![P2P network](images/P2P-network.png)

P2P networks became popular in file-sharing applications like Napster and BitTorrent, which are typically associated with illegal downloading and piracy. P2P networks are usually recommended for private households or small businesses – they are **inexpensive to set up**, but **security issues** can create expensive problems.

### P2P Security

Security is challenging in P2P networking for two reasons:

* P2P software has to be **downloaded** to become part of the network, making it especially vulnerable to remote exploits. 
* Every peer has an equal network connection because of **interconnectivity**; therefore, a malicious participant could send incorrect requests or returns, as well as distribute malware and corrupted data through the entire network. Other security risks are denial of service (DDoS) attacks, routing attacks, and routing network partitions.

Hashing, chunk verification, and a higher degree of encryption are means to mitigate security risks in P2P networks.

### Are P2P networks decentralized, distributed, or centralized networks?

P2P networks can be decentralized, distributed, centralized, or a mix. When a system has different components which combine P2P elements with other networking concepts, it can at the same time have parts typically known as distributed but also include centralized aspects.

The two P2P services mentioned earlier, Napster and BitTorrent, include aspects typically ascribed to distributed *and* centralized networks.

<ExpansionPanel title="Approaches to P2P: Napster vs BitTorrent">

**Napster** is a music-focused file-sharing service. Its earliest version used **distributed data storage**, since music files were distributed through peers and not stored on a central database. However, a **central server** was used to manage the peers. Napster combined a distributed P2P data storage with a central managing authority, the Napster server. After the Recording Industry Association of America (RIAA) sued Napster for facilitating the sharing and transfer of copyrighted material, Napster shut down its original P2P network in July 2001.

**BitTorrent** is another P2P file-sharing service that is also used to share music. Like Napster, BitTorrent uses a **data storage among peers**. However, it has a **decentralized network structure** since there is no central server. BitTorrent also faced legal complaints due to allegedly facilitating copyright infringement through illegal downloading. But this time, the case was not so clear as with Napster. Why?

Because of BitTorrent's decentralized coordination of peers, there was no central server that could be turned off to shut down the network.

These two examples show how **network design and structure** choices can have far-reaching impacts. Knowing how P2P networks work is essential in understanding blockchain technology. Just think about the similarities between P2P network architecture and the network structure of blockchain applications.

</ExpansionPanel>


## Blockchain as a merging of data storage and network

Historically, data storage and networks have been **treated separately**, mainly because the former was adopted long before the latter. Networks were built first, and data storage was connected afterward.

Blockchain merges these two concepts by combining elements of a database with a P2P network. Blockchains store data in the same way as a **decentralized database**, and also use P2P networking.

A blockchain can be understood as a **data structure** since it has a certain manner of storing and organizing data, but at the same time it is also more than a database: a blockchain collects data values or attributes, but it also includes their relationships and enables a set of possible functions and operations.

![Blockchain as a data structure](images/blockchain-data-structure.png)

If we imagine a blockchain as a computer, it would have three layers: **database**, **network**, and **state**. The entire computer is a collection of blocks where every new block represents an update to the state layer.

All **data** (such as currency transfers, smart contract code, or calls of function) is encoded in **transactions**, which are bundled into blocks and must be validated. Remember, data cannot be deleted or altered after being stored on a blockchain.

![Blockchain computer](images/blockchain-computer.png)

The blockchain network layer is comprised of **nodes**. As previously stated, each node has a copy of the chain of blocks. Nodes are usually given equal power, but power distribution depends on the deployment pattern of the blockchain.

Currency transfers and smart contract implementation is done by adding transactions to the blockchain, which will again be bundled into a block and verified. To interact with the state layer of the blockchain computer, a user can send transactions or view information by coupling an application with a node. Smart contracts can then be used to interact with transactions.


## Further Learning

* [Slepak, Greg (2015): Deconfusing Decentralization - a very good introductory video on the concept pf decentralisation](https://www.youtube.com/watch?v=7S1IqaSLrq8)

* For a quick and clear explanation of blockchain in action, watch this video: [How Does Blockchain Actually Work?](https://www.youtube.com/watch?v=Za5lPKNV_Mk)


## Next up

xxxxxxxxxxxxxxxxx
