---
title: "Introduction to Blockchain"
order: 2
description: An overview of blockchain technology
tag: fast-track
---

# Introduction to Blockchain

This first section is intended to provide you with a basic knowledge of what blockchain is and the benefits it offers, as well as introducing some important general terminology that will help you through the rest of the course.

<HighlightBox type="learning">

This section will cover:

* Blockchain in 100 words
* What exactly is a block? What exactly is a blockchain?
* What is a ledger?
* What is a node?
* Centralized vs Decentralized vs Distributed Networks
* What is Consensus?

</HighlightBox>

## Introduction

In the last few years, “blockchain” has become almost a household term. With the likes of “Bitcoin” and “NFTs” dominating news headlines around the world, it’s almost certain that everyone has at least heard about it, even if they’re not really sure what it is. So, before going any further, here is a simple, high-level definition of what blockchain is all about:

**Blockchain is a reliable method of shared record-keeping that doesn’t require trust to function**.

Don’t worry if you still have some doubts – why that definition includes the word “trust”, for example, might invite a question – you’ve only just started, after all! By the time you reach the end of this chapter, you’ll be able to hold your own in any casual conversation on the topic that seems destined to change the world.

### Blockchain in 100 words

It is important that you understand the most basic characteristics of blockchain from the beginning. The following statements summarize its key features in brief:

<HighlightBox type="info">

**Blockchain technology**:

* provides a way to securely store and maintain a constantly updating database, or **ledger**, which is duplicated across a **distributed** network.
* uses **consensus** between participants to process legitimate transactions and protect the ledger against loss or error, removing the need for a **centralized** authority which demands network trust.
* preserves the privacy of its users and the confidentiality of transactions, even though every **node** on the network holds a copy of the ledger.
* can maintain functional integrity and data security even if a significant minority of nodes are subject to failure or attempt to attack the network.

</HighlightBox>

Some terms in that description may be unfamiliar – including the literal meaning of the word “blockchain” itself – but during this course you will encounter accessible definitions and examples of these and other features of blockchain technology. For now, to further establish these basics, the following questions will clarify the highlighted terminology.

## What exactly is a block? What exactly is a blockchain?

The second module of this course will explain the mechanics of blockchain in an accessible way, but put simply:

* A **block** is *a collection of data in a fixed order* (for example, financial transactions recorded in the order they occurred).
* A **blockchain** is a series of such *blocks*, *chained* together in a fixed order (each new block is always added after the previous block).

By following these two steps – creating well-ordered blocks of data, and well-ordered chains of blocks – an **immutable history** of network activity can be achieved: an unchangeable *ledger* preserving a record of all transactions, from the beginning until the present moment.

This leads into the next question:

## What is a ledger?

A **ledger** is *a chronological record of transactional activity*.

For centuries, accountants have kept record books of in-coming and out-going transactions in a very intuitive way: on each fresh page, the first transaction goes at the top and newer ones are added underneath as they occur. This preserves the evidence of what came before, and provides valuable context for the activities of the future.

Ledgers are a logical and reliable methodology, and blockchain is simply an implementation of the same idea for distributed networks: instead of one “accountant” keeping the ledger for everyone else, each *node* carries a copy of the ledger, kept up-to-date in almost real-time.

## What is a node?

**Node** is common term for a single member of a network. The device on which you are accessing this course is likely a node within your organization’s IT network; your cell phone is a node in the telecommunications network of your service provider; in a sense, *you* are a “node” within the “network” that is your family, or your circle of friends, or of your colleagues.

*Are there differences between these examples of networks? What categories of networks are there?* And to return to the opening definition of blockchain, *Why is trust important?*

These questions are critical to how and why blockchain is implemented.


## Centralized vs Decentralized vs Distributed Networks

In general, networks are typically *centralized*, *decentralized*, or *distributed*. Some networks can be decentralized *and* distributed, but these are the three basic types.

### Centralized Networks

**Centralization** is the traditional method of network organization. There is one authority which has control over the activities of the system: all transactions between network participants must pass through it to be legitimized, and it preserves a historical ledger to ensure that no one can deceive the network about their status.

<!--IMAGE MISSING-->

An example of centralization is a bank (the authoritative node) and its customers or account holders (the rest of the network). All transactions must go through the bank, where key checks are made: *Do you have the money you want to transfer? Are you sending it to the correct recipient? Are you who you claim to be?* Importantly, this central node is also where *a historical record of all transactions is preserved for future reference*. The system must recognise activities of the past for the activities of the future to be considered reliable.

As long as everyone trusts the bank, centralization works: data is private, and no one can access a particular account without the permission of the bank and the account holder. But if that central node is compromised, the entire system is compromised as well. What if a bad actor changed the ledger to add transactions you didn’t agree to? What if due to a technical fault the bank’s data was lost or corrupted? Centralization has its risks.

### Decentralized Networks

**Decentralization** can be seen as a structural expansion of centralization. Instead of a single network which “bottlenecks” through one authoritative node, decentralization is more like a network of networks: subgroups of nodes connect to a “local” point of authority, which in turn connects to other points of authority across the network as a whole.

<!--IMAGE MISSING-->

To maintain the bank example, a decentralized network is like having regional branches which communicate directly with the head office (and possibly each other), each one working on behalf of subgroups of regional account holders.

This approach increases systemic security. Instead of all nodes being forced to interact only through one central authority, they are grouped around different but associated authority nodes, which optionally allows the ledger of network activity to be duplicated and stored at multiple trusted locations. This makes the ledger more resistant to accidental or deliberate compromise, but it does *not* make it immune, and other potential problems remain. If a key node fails, other network activity can continue; however, communication across the network could be impeded, and the copies of the ledger on either side of the failed node could become inconsistent, leading to all sorts of confusion both in the moment and in the future.

### Distributed Networks

**Distributed** networks attempt to solve the flaws inherent in centralized and decentralized alternatives. In essence, the distributed network abandons using points of authority at all – it’s like proposing a banking system with no head office or branches, just account holders.

<!--IMAGE MISSING-->

At first this may seem like a disaster waiting to happen. Without an authority to preserve the record of past transactions and enforce healthy network behavior, how can all the nodes trust each other to perform legitimate transactions, or detect if they do not? Each node would need to hold the complete transaction history of the network in order to trustingly transact with any other node. This would be like sharing your private data with people you had never met, including those you aren’t even planning to do business with.

What makes blockchain revolutionary is that it solves the problems that make a distributed network sound unfeasible, allowing individual participants to take advantage of its strengths.

Blockchain provides a system that allows all nodes to hold an up-to-date transaction record of the entire network, while preserving the secrecy of both individual user identities *and* the details of transactions between them. This delivers two significant benefits over the other network types:

* Taken as a whole, communication across the network is more robust. Any failure of a given node does not compromise the ability of the larger network to function.
* Because every node has a copy of the network’s transactional record, any accidental or deliberate compromising of that data can be rapidly detected and corrected, simply by comparing it with the consistent data populating the rest of the network.

However, one thing is not yet clear: *how does a network with no centralized authority decide what goes into the shared ledger?*

The answer is, **consensus**.


## What is Consensus?

If a group reaches **consensus**, they share a general agreement about a particular subject. In the context of blockchain, an essential goal is for the network to reach a consensus about the state of their shared ledger.

<HighlightBox type="info">

Consensus typically implies at least the possibility of a choice between options. Therefore, the concept is largely irrelevant in *centralized* networks: as there is only one ledger, owned and modified by the central node, there is no alternative for the network to compare it to.

As networks become more *decentralized*, it becomes possible for multiple copies of the ledger to coexist at different authoritative nodes. Should discrepancies between the copies arise, there is a necessity for consensus regarding which version of the ledger is correct – but involvement in determining this remains limited to the authoritative nodes.

**In distributed networks, all nodes have coexisting copies of the ledger**. This means that, for the network to function properly, true consensus among the nodes is vital – without collective confidence about the past activity of the network, future activity cannot be trusted.

</HighlightBox>

The mechanisms used in blockchain to achieve network consensus will be explained in the second module, but in general blockchain achieves two goals:

* Potentially *any* node can update the shared ledger in a verifiable manner – even if other nodes don’t know who performed the update, they can check its validity.
* It provides a system by which nodes can evaluate differences between copies of the ledger and reach a collective consensus regarding which is the authoritative version.

As a result, there is no longer a need for a trusted authority to oversee the network. Instead, trust becomes an emergent property of a trust-free system.


## Further learning

<HighlightBox type="link">

<!--PLACEHOLDER-->

</HighlightBox>


## Next up

You have started by looking at the basics of how blockchain works. In the next section, you will look at the place of blockchain in the future of the internet, and have an introduction to Cosmos.
