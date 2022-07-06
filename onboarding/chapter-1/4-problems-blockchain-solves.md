---
title: "What Problems Does Blockchain Solve?"
order: 5
description: Double-Spending, Byzantine Faults, and Data Security
tag: fast-track
---

# What problems does Blockchain solve?

## Introduction

In a sense, the central problem blockchain solves is exactly that: *centrality*, the reliance on a single point of authority, one which simultaneously wields power over many mere users while being a key point of potential systemic weakness. However, there are some more specific issues which blockchain was specifically designed to resolve.

<HighlightBox type="learning">

This section will cover:

* The Double-Spending Problem
* The Byzantine Generals Problem
* Information Security on Blockchains
* Public-Private Key encryption

</HighlightBox>


## The Double-Spending Problem

The importance that is placed on physical artifacts may be arbitrary, but they have actuality – the value of gold may change, but a ring on your finger is unique and tangible: no one else has *that* piece of gold. Now compare this to the idea of *digital* artifacts, and the ease with which they can be copied: an image of that ring can be *duplicated infinitely*, and *identically*. This presents obvious problems if digital artifacts are intended to represent assets with value. 

This problem is amplified if you consider a digital form of currency. What prevents someone from making a copy and spending the same unit of currency twice? This is known as **double-spending**, and the *double-spending problem* refers to the challenge of designing a cash system in which currency units are digital artifacts but can't be spent more than once.

<!--IMAGE PENDING-->

In the traditional financial system, double-spending is avoided because centralized third parties (like banks) are trusted to manage and control all transactions. It is generally not possible for two parties to exchange value online without involving a trusted third party to handle the settlement process and update their ledgers, as well as the account balances.

In 2008, [Satoshi Nakamoto presented an alternate solution](https://bitcoin.org/en/bitcoin-paper): replacing these centralized ledger-keepers with a decentralized and distributed ledger maintained by a large network. Each member of the network has an exact replica of the ledger, and no one can update it without forming a consensus – like a large crowd of witnesses who have to agree on proposed changes and won't allow certain events to occur, such as spending the same funds twice.

You will encounter an accessible explanation of exactly how blockchain achieves this protection against double-spending in Chapter 2 of this course.

This was the origin of Bitcoin, and it demonstrated that a network of participants who don't necessarily trust each other can still achieve consensus about the validity of a transaction, its history, and the resulting state of the ledger. Centralization was no longer a necessity.

This leads into the other problem facing a distributed network: *maintaining consensus*.


## The Byzantine Generals Problem

Imagine that three armies lay siege to a fortified city. All roads into the city are blocked and the terrain between them is filled with dangers, so the defenders have no escape, but the battle is not yet won. The success or failure of the armies is contingent upon communication: the city's defenses are strong enough to destroy any one or two of the armies if they attack alone, but the city will fall to a coordinated attack by all three. The generals must agree either to attack all at once or not attack at all, but how secure are their messages?

<!--IMAGE PENDING-->

Each general faces several potential problems:

* The surrounding land is dangerous, so messengers may be lost traveling to and from each army, or a general could die without the other two even knowing about it – *How can you know your message was received?*

* Worse, each general cannot be certain that the others are loyal, one or more generals could secretly plan not to attack at the agreed time – *What if my allies cannot be trusted?*

* Even if all three generals are loyal to each other, some enemy agent could try to intercept and replace legitimate messages with deceitful or nonsensical information. *What if other messages are unreliable?*

So, confronted with all these challenges, *What do the generals do?*

This thought experiment is known as the *Byzantine Generals Problem*, and the challenges it presents map very usefully onto distributed networks:

* The generals become nodes of equal status, sending data through unsecured communication channels.
* Data could be lost, or corrupted, or replaced with malicious alternatives.
* Nodes might drop out of the network, or actively work to undermine the shared objective.

The difference is that, instead of only three generals trying to collaborate, there could be *thousands* of nodes; and obviously, instead of attacking a city, they need to agree on the state of a shared, ever-changing ledger.

### Byzantine Fault Tolerance (BFT)

Achieving consensus about *the truth* is the critical challenge in a hierarchy-free, permissionless, and failure-prone network – and in a distributed network there is no one authoritative ledger-keeper to turn to for confirmation. The bad news is that the Byzantine Generals Problem is provably unsolvable, but there *are* strategies to mitigate it. Systems which successfully do so are considered to have **Byzantine Fault Tolerance** (BFT).

In essence, **blockchain is a Byzantine fault-tolerant networking system**. It allows you to interact with unknown peers in a reliable way, but without granting anyone unwarranted trust or authority; it both generates *and* secures a verifiable historical record by its collective, cooperative nature; and it balances the security of work being done in the public eye while maintaining the individual privacy of its users.


## Information Security on Blockchains

At the beginning of this course, a serious problem was identified with implications for any distributed, decentralized network: *If every node on the network holds a copy of the shared ledger, how is user privacy or data confidentiality maintained?*

In a centralized network, this is a less significant problem. To return to the banking example, any transactions you make are only known to you, the recipient, and the bank or banks involved. All other customers of the banking system are completely oblivious to your activity, and you trust the banks to prevent information about your activities from being accessed. 

Of course, the direct participants in your transaction must know who each other are and what they are doing, and to an extent this is true in all banking. Even banks that offer "anonymous" accounts have to retain some corroborating data about who their customers are; and, of course, the owners of these accounts have some knowledge of who they send their money to, even if the record shows only mysterious numbers instead of names; but as with regular banking services, such records of transactions are kept carefully private.

Things are very different on a blockchain-based network. All the participating nodes will receive updated versions of the ledger, meaning any transactions which have taken place will be visible to them, regardless of whether they were direct participants in a given transaction or not. So how can confidentiality be achieved on a blockchain?

### What is a transaction?

There are three elements to any transaction, on blockchain or in the real world. It requires:

* A **sender**
* A **receiver**
* A **package**

The "package" could really be anything. It could be a physical object: a gift, a letter or parcel, a handful of cash money. Or it could be digital, like an email or text message. In blockchain it would be data of some sort, for example a payment in cryptocurrency.

<HighlightBox type="note">

In this context, "a transaction" must be broken down to its most atomic form. To illustrate this, the process of *making a purchase* actually requires **two** transactions:

* from A to B, to send the payment.
* from B to A, to send the purchased goods.

</HighlightBox>

With these details in mind, how much of this information *needs* to be made secret for a person to feel that a transaction on a blockchain is sufficiently confidential?

### Secrecy where necessary

Cryptocurrency will provide a simple case study. Imagine Alice wants to send one Bitcoin to Bob. You can immediately identify the three necessary elements of the transaction:

* Alice (the **sender**)
* Bob (the **receiver**)
* 1x Bitcoin (the **package**)

However, not all these elements absolutely *need* to be secret for user confidentiality to be maintained: if the identities of Alice and Bob are disguised, the transfer of currency could be between any two users of the network. Therefore, Alice and Bob need a method of knowing who each other are so they can make the transaction but without anyone else being able to identify them.

However, the solution – a clever system called **Public-Private Key encryption** – actually goes one step further: it allows Alice and Bob to collaborate on their transaction so that not only their identities but also the detail of their transaction can remain confidential.


## Public-Private Key encryption

Instead of using their true identities, each user of a distributed network can chose more or less anything as their identity – similar to the anonymous numbered accounts of secretive banking systems, users don't have to go by their real names. This means there is already a layer of anonymity between a user's personal life and their presence on the network.

In addition, each user has two linked **encryption keys**: one is **private**, which they never share with anyone else, and the other is **public**, which they can freely share with anyone. Any message that is encrypted with the private key can only be read if it is decrypted with the public key. 

<HighlightBox type="tip">

This system can be used in a number of ways, for example to prove that when you send a message that it was genuinely written by you: 

* You write a message, and encrypt it with your *private* key.
* You send the message to the recipient.
* The recipient decrypts it with your *public* key.
* Therefore, only you could have written the message.

</HighlightBox>

This system is the foundation for confidentiality in blockchain. In an extremely simplified sense, Alice and Bob are able to use a combination of *both* their public and private keys to perform a transaction that will effectively be unreadable to anyone except themselves – so the detail of their transaction becomes confidential too.

Provided that the transaction itself is valid (that Alice has the funds to send, and Bob receives them) it will be included in a new block and added to the chain of previous transactions. There it will be visible to anyone holding a copy of the ledger, but none of them will be able to access the details of it.

This, along with other practical aspects of how blockchain actually works, will be explored further later in this course.


## Further learning

* ???


## Next up

In the [final section](ADD LINK HERE) of Chapter 1, you will look at the different categories of blockchain networks and examine some real-world use cases that demonstrate the diverse ways in which blockchain technology can impact various different global industries.

