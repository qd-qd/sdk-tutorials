---
title: "What Problems Does Blockchain Solve?"
order: 5
description: Double-Spending, Byzantine Faults, and data security
tag: fast-track
---

# What problems does Blockchain solve?

In a sense, the central problem blockchain solves is exactly that: *centrality*, the reliance on a single point of authority, one which simultaneously wields power over many mere users while being a key point of potential systemic weakness. However, there are some more specific issues which blockchain was specifically designed to resolve.

<HighlightBox type="learning">

This section will cover:

* The Double-Spending Problem
* The Byzantine Generals Problem
* Privacy on Blockchains

</HighlightBox>

## The double-spending problem

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

## Privacy in blockchains

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

### Privacy where necessary

Cryptocurrency will provide a simple case study. Imagine Alice wants to send one Bitcoin to Bob. You can immediately identify the three necessary elements of the transaction:

* Alice (the **sender**)
* Bob (the **receiver**)
* 1 Bitcoin (the **package**)

However, not all these elements absolutely *need* to be secret for user confidentiality to be maintained: if the identities of Alice and Bob are disguised, the transfer of currency could be between any two users of the network. Similar to the numbered accounts of secretive banking systems, users don't have to go by their real names. This means there is already a layer of anonymity between a user's personal life and their presence on the network.

However, Alice and Bob would still need a method of confirming who each other are, so they can make the transaction with confidence that they are interacting with the intended person. The solution to this problem is basically the same as the one people have used in the real world since the invention of writing: **Identity is confirmed by using a signature**.

### Signatures

When you sign your name on a job contract, or sign for a parcel delivery at your door, in effect you are using a unique and verifiable symbol to represent your identity. You always use the same signature, even in different contexts, and it is used as a "proof" that the person holding the pen is who they claim to be. And objects can also be signed as a form of proof, such as when an artist signs their name to a painting, confirming its authenticity.

Users of distributed networks use a clever methodology called **Public-private key encryption** to achieve these same kind of proofs – but this kind of signature is impossible to forge! 

In simplified terms, everyone on the network has a two linked encryption keys: one that can be used by anyone else, and one that they keep secret. To prove that a transaction is legitimately yours, you "sign" it using your **private** key. No one else can do this, but *everyone* else can use your **public** key to confirm your other key made the signature.

Public-private key encryption can achieve impressive things. For example, Alice and Bob could use a combination of all four of their public and private keys to establish a secure channel of communication, inaccessible to anyone except themselves – so the detail of their interaction through that channel can be absolutely trusted. This, along with other practical aspects of how blockchain privacy works, will be explored further later in this course.

Signatures are used this way to "identify" participants on the blockchain while preserving their privacy on a general level through user anonymity. While the detail of a transaction could be viewed by any node holding the shared ledger, nothing automatically connects a particular account with a specific person in the real world; nor are users limited to a single presence on the network, so their transactions could be intentionally spread across multiple accounts, further obscuring their business from public knowledge.


## Further learning

* ???


## Next up

In the [final section](ADD LINK HERE) of Chapter 1, you will look at the different categories of blockchain networks and examine some real-world use cases that demonstrate the diverse ways in which blockchain technology can impact various different global industries.

