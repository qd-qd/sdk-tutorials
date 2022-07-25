---
title: "Privacy and Knowledge"
order: 5
description: What do you know, and how do you know it?
tag: fast-track
---

# Privacy and Knowledge

In an environment where anonymity is typical, access is public, and transactions can carry financial and informational value, desires such as personal privacy and data confidentiality come into conflict with the need for trust in who you are interacting with, and confidence in the validity of any information that is shared. This may seem like an intractable problem, yet there are strategies available that provide elegant and effective solutions.

<HighlightBox type="learning">

This section will cover:

* Public-private key encryption
* Ring signatures
* Can you entrust confidential data to a blockchain?
* Merkle trees
* Merkle proofs

</HighlightBox>

## Public-private key encryption

In the [previous chapter](ADD CH1-MOD4 LINK HERE), you briefly looked at the subject of **signatures** and how they can confirm the authenticity of any transaction made by a user. This is particularly important for the purposes of blockchain, so the mechanics of the process deserve deeper exploration.

When a user interacts with the network, they rely on two linked **encryption keys**: one is **private**, which they never share with anyone else, and the other is **public**, which they can freely share with anyone. **Anything that is encrypted with the private key can only be decrypted with its public key, and vice versa.**

This is an important detail. It is like a safe with one lock but two keys: one key only turns clockwise and the other only turns counter-clockwise. If you lock the safe with the clockwise key, only the counter-clockwise key will unlock it – you cannot use the same key twice to open the safe.

This system can be used in several ways, for example, to send a message that you know only the recipient can read and that they know only you could have written.

### Sending a private message in a public environment

Imagine that Alice wants to send a message "for Bob's eyes only", which he can be sure is from her, but they are using a network where everyone can see everyone else's behavior. Using public-private key encryption, there are four starting conditions:

* **Only Alice** knows _Alice's **private** key_.
* **Only Bob** knows _Bob's **private** key_.
* **Everyone** knows _Alice's **public** key_.
* **Everyone** knows _Bob's **public** key_.

How does Alice send her message privately?

1. Alice writes a message she only wants Bob to be able to read.
2. Alice also writes a "signature", which can be any sort of additional information.
3. Alice encrypts the signature using **Alice's** *private* key.
4. Alice collects the message, the original signature, and the *encrypted* signature into a package, which she encrypts using **Bob's** *public* key.

Now Alice sends the package to Bob. What happens next?

1. Bob decrypts the package using **Bob's** *private* key, and can now read the message – no one else has this key, so even if someone intercepted the package they would not be able to read its contents.
2. Bob decrypts the encrypted signature using **Alice's** *public* key.
3. If the decrypted signature matches the original signature, he knows _only someone with Alice's **private** key could have encrypted it_.
4. Therefore, Alice must have been the sender.

It is important to note that, at the end of this interaction, _Alice is **still** the only person who knows her private key, just as only Bob knows his_. They can go through this process again or Alice could communicate with someone completely different, but she can still use her private key with certainty that no one else has access to it.

## Ring signatures

An interesting extension of this public-private key system is the **ring signature**, which provides an additional level of anonymity beyond that of blockchain networks generally.

Imagine an online voting system, in which you participate by sending a "vote" transaction that indicates your preferred candidate. Using blockchain would provide some real advantages: an immutable record makes tampering with the results impossible, and the law of "one person one vote" is guaranteed as double-spending is prevented. However, with the provenance of each and every transaction so strongly established, how to maintain the anonymity of an individual's vote is less clear.

Ring signatures offer a solution to this issue, by congregating the transactions of a set of participants in such a way that their individual signatures cannot be distinguished after the fact, but in which each participant can still confirm their transaction was recorded correctly. In a voting scenario it would work like this:

1. At any point during the registration period, each voter adds their **public** key to the ring signature to indicate their intent to vote. Unless someone can spy on this step, it is not possible to deduce any specific public key from the before-and-after states of the collective ring signature.
2. During the voting period, everyone votes by sending a transaction encrypted with their **private** key. Again, unless an observer had an unlikely ability to detect the origin of individual transactions, no one would be able to know who voted a particular way – only the users who registered were now voting one after another.
3. At the close of voting, the blockchain provides a tamper-proof record of the collective voting results, but the ring signature provides confidentiality regarding how each participant voted. There is no possibility of any successful vote transaction not being counted.

After the votes are tallied, individual voters can easily audit their vote if they wish to confirm their intent was registered legitimately. With their private key, they alone can distinguish which vote in the ring signature is theirs, and check to see that it has increased the tally by `1`.

The applications for ring signatures face limitations of scale, as large sets of participants will overload them, but for smaller groupings they are effective. To continue this example, implementing them at the precinct level and then aggregating the results would allow the benefits to be enjoyed by a larger system. The precincts could also enforce permissions so that a particular voter could only participate once and at the appropriate location.

## Can you entrust confidential data to a blockchain?

You have already seen [examples of potential use cases](ADD LINK TO CH1-MOD5 HERE) for blockchain applications that move out of purely financial fields, for example, government services or healthcare information. How would that work on a practical level though? Would you feel comfortable having your medical records held on a distributed network?

In practice, this would never happen. Storage space on a blockchain is costly, so it would not be economically sound to house vast numbers of detailed official documents in this way. However, there are practical alternatives to storage in this literal sense. A common solution utilizes [hashing](ADD LINK HERE) and [smart contracts](ADD LINK HERE): instead of the blockchain holding a copy of some actual documentation, it holds its *hash* in a smart contract, with the actual document (for example, your driver's license) stored off-chain.

The smart contract would also embed significant supporting information, such as the origin and lineage of the document, the on-boarding process that added it to the chain, etc., such that the hash can be considered an authentic representation of the original. This means that, when presented with the actual document, an observer can easily confirm its authenticity by hashing the document and comparing it with the hash in the smart contract.

If an on-chain hash of an official document becomes authenticated like this, ways for the information it contains to be utilized can come into effect that have real-world parallels. For example, imagine you needed to confirm your date of birth. In everyday life, showing your driver's license, passport, birth certificate, or similar official documentation would be immediately accepted as genuine proof. An authenticated hash of such a document could achieve the same purpose for on-chain activities, and by using **Merkle trees** you can also maintain close control of exactly what data you choose to share.

## Merkle trees

A **Merkle tree** is _a data structure in which each parent node includes the hash of all its child nodes_. The outermost "leaf" nodes contain only the hash of their data block, while the "Merkle root" hash effectively contains the hashes of all data in the entire structure.

As you saw in the previous discussion of hashing in blockchains, this means any change to the data within a Merkle tree would result in a cascade of changes to all the subsequent hashes, making it very easy to confirm data integrity. Integrity can be checked even if data is incomplete, such as during downloads, since branches of a tree can be confirmed as valid before the whole tree is available.

The use of chained hashes means that corrupted, or merely altered, data can be quickly identified, investigated, and corrected, as any change to a node produces a cascade of altered hashes that can be traced back to the cause. They are generally powerful tools for verifying large quantities of data, which makes them very attractive for blockchain networks. In a blockchain, each block header keeps the hash of the root (top node) of one or more Merkle trees.

This structure could also allow you to make targeted use of the data included in the on-chain representation of an official document, through the use of a **Merkle proof**.

## Merkle proofs

Imagine again that you are required to provide proof of your date of birth. You have on the blockchain a smart contract that can verify your passport information, uploaded to the network by your nation's issuing authority. Therefore, it is considered a highly trustworthy data source. Your passport naturally contains a variety of important information, including:

* Your name
* Your date of birth
* Your gender
* Your nationality
* Your place of birth
* The passport number
* The passport's issuance and expiration date
* Your signature

The Merkle tree of your passport document could look something like this:

<!--INSERT MERKLE-IMAGE 1 HERE-->

The "leaf" nodes at the bottom tier only contain hashes. Each piece of original data is **not** included on the chain, and because a hash cannot be reversed to reveal the data it encrypts, the actual information on your passport is not made public in any way.

These hashes are combined in pairs on the next tier up, and these nodes are then hashed in turn. You will recognize similarities to how a basic blockchain structure functions, except here each of these "non-leaf nodes" contain the hashes of exactly two nodes below. This procedure is repeated until you reach the "root" node of the Merkle tree. The hash of the root node, therefore, includes the hashes of all of its child nodes, right down to the leaves.

There may of course be much more information than this on a passport – a record of places you have traveled to and when, for example. You could certainly use this document to prove your date of birth, but you may not wish to share *any* of this additional data when you do. A **Merkle proof** allows this.

### Controlling data exposure with a Merkle proof

How do you use this Merkle tree to prove your date of birth?

1. You simply *tell* the requestor of information your date of birth. They do not yet have reason to accept this information as true.
2. Next, you provide access to your trusted documentation tree, which reveals only a coherent hierarchy of undifferentiated hashes.
3. Finally, you identify the leaf node which contains the hash of your date of birth:

<!--INSERT MERKLE-IMAGE 2 HERE-->

With this information, the requestor can easily generate their hash of your date of birth and test it against the accumulated hash values of the Merkle tree. If there is no discrepancy, this confirms that the date of birth you provided does indeed correspond to the leaf node. If the passport Merkle tree was uploaded by an impeccable real-world authority, your assertion can be trusted – all without revealing any further information than you intended.

## Further learning

* ???

## Next up

The [next section](ADD LINK HERE) will build on the introduction to Cosmos from [Chapter 1](ADD LINK HERE) with a closer exploration of various features of Cosmos.
