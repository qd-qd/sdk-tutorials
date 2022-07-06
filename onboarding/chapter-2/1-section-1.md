---
title: "Ledgers, Blocks, and Hashing"
order: 2
description: How blockchain reinterprets ancient strategies
tag: fast-track
---

# Ledgers, Blocks, and Hashing

## Introduction

You've already looked at what blockchain is – *a distributed ledger* – so now it's time to dive into how blockchain does things differently, adapting a basic concept for use in a complex world.

<HighlightBox type="Learning">

 This section will cover: 

* Ledgers: a Historical Context
* Hashing: Calculating Trust
* Strength in Numbers

</HighlightBox>


## Ledgers: a Historical Context

The idea of the **append-only ledger** has been known and embraced for centuries. It is a chronological record of activity, like a book with vertical columns of transactions, the oldest at the top of the page and newer ones underneath it. It's a simple, logical, and reliable methodology, but in the ages before digital technology it had a few obvious weaknesses.

Physical records are prone to decay and destruction, not to mention theft or just revision by unscrupulous actors. Fire, flood, and the passage of time can wipe out a history completely, while erasing lines or tearing out pages could be as effective a crime as robbing a bank. They're also hard work to duplicate: pre-computers, backing up records meant filing cabinets full of hardcopies, taking up costly storage space. Worse, before the 20th Century, even a single backup of a record book would be a luxury, requiring someone to copy the original ledger by hand (with the constant possibility of making errors in the process).

Blockchain is nothing more than a new implementation of that ancient strategy. In a digital context, instantaneous and flawless duplication of records is second nature; this fact alone means distributing copies of a ledger across a network is at least viable. The question is, can each copy of the ledger be trusted equally, as if they were still a single document?

Blockchain is an affirmative answer to that question, but before clarifying exactly how it does so, there is a significant difference between traditional ledgers and blockchain that needs to be addressed.

### What is a block?

Returning to the traditional ledger, how does this map onto blockchain? What is *the block?* After all, there are several aspects that could be grouped together: the descending list of transactions that fill each page; the different pages that form a book; eventually even the completed books filling the shelves that take up all the space in an accountant's office.

In this example, one "block" in the blockchain would most logically be *a page*. But instead of a book, or even a shelf of books, each node of the network is a folder waiting for a new page to be added to it. Transactions are recorded chronologically on a page; when the page is filled, it is duplicated and sent to each node's folder, where it is added chronologically to the pages that came before; thus everyone has the same information.

This simplification hides *gigantic* complexity, but in essence this is what is meant by a chain of blocks: *groupings of transactions made within a given time period, which are recorded sequentially*. Weighty questions are raised by this approach to networking, though, starting with the fact that transactions may include extremely valuable or private information – how can security and confidentiality be maintained on a public network where everyone has a copy of the data?

This is an important issue, and is examined [later in the chapter](ADD LINK?), but there is more than one sense in which *trust* is vital to blockchain. Fundamental to the system is ensuring confidence that the blockchain which propagates through the system really *is* the same at every single node. This is achieved through one of the key cryptographic features of blockchain: **hashing**.


## Hashing: Calculating Trust

Blockchain is moving digital technology away from centralized modes of trust, but it still needs to maintain the protections they provide. It's purpose could be defined as to create a publicly available, verifiable record of transactions, *while also protecting the data inside those transactions*. **Hashing** is part of how this challenge is resolved.

A **hash function** is a mathematical process which takes a data set of arbitrary size and generates a unique(ish) fixed-size value, called a *hash*. One benefit of this is that even huge inputs can be converted to much more manageable (and consistently sized) outputs; another is that the resulting hash shares no qualitative characteristics with the input that created it – any hashes created by a particular function are superficially the same as each other. In other words, you can't discern anything about the input simply by looking at the output.

An effective hash function should be computationally fast while minimizing the possibility of any two inputs producing the exact same output. For blockchain, hashing delivers rapid and robust error checking, by which nodes can confirm the integrity not just of each new block on the chain, but of the entire history of that chain right back to its original "genesis" block.

Let's illustrate how this works a little more directly.

### Using Hashes to Ensure Block Integrity

In this example, a block is represented using only a simple phrase rather than many pieces of ordered data: for example, instead of an entire play by William Shakespeare, just the words *Romeo and Juliet*. After encrypting the "block" phrase (in this case using the SHA-256 hashing function favored by Cosmos) the result is this:

 **Input phrase**:
 Romeo and Juliet
 **Output hash**:
 b15a06302f4dc7a0acf945f1c670e9f0666af3078f3dea2a62c42e25b837df32

This output hash is in **hexadecimal** format. Unlike the everyday decimal numbering system, using digits from 0-9, hexadecimal uses sixteen digits, 0-9 *and* the letters A-F. It's a little strange at first sight, but a simple illustration would be to compare how they represent "nine" (both are the same, "9" and "9") and "ten" ("10" in decimal, "A" in hexadecimal).

Returning to the example's output hash, this 32-byte hexadecimal string is unique to the input phrase – if you want to prove it, try it for yourself [here](https://www.browserling.com/tools/all-hashes) and you'll get the exact same 64 characters. 

Now, what happens if you change the input phrase even very slightly?

 **Input phrase**:
 Romeo and *Julie*
 **Output hash**:
 a580e89a80762689530b4227699aa600e3402ba074c4a4593823a5f1d5a9e451

By changing just a single character, deleting the "t" from "Juliet", the output hash becomes unrecognizably different. Also, the length of the hash doesn't give any clue to the content of the input phrase: if you really did input the entire text of the play, it would *still* give you a unique output no longer or shorter than the previous examples.

What this achieves is a way to have instant knowledge about the content of a block without having to first review every transaction inside it. If two nodes show different hashes for "the same" block, you know with absolute confidence that their content is **not** the same. This ease of integrity checking is a fundamental feature of blockchain, where the motto is **Don't Trust: *Verify***.

You will see more on this subject when you look at how blocks are accepted onto chains later in this chapter.

### Hashes as the Foundation of Blockchain

Now imagine a Shakespearean blockchain: *an append-only ledger in which new plays are periodically added after old ones*. Could it look like this?

<!--

INSERT TABLE1 IMAGE

-->

If the plays are supposed to be *ranked in the order of their publication*, from old to new, the answer is yes. However, **is this chain a *trustworthy* record of the publication order**?

The answer is, **Definitely Not**.

These hashes certainly make it easy to detect if the text of any one play is altered: simply generate its hash again and compare; if the hashes are different, then the content has changed. However, *the order in which blocks are added to the chain* is vital to blockchain applications. Here, swapping the positions of any two plays could easily go unnoticed in a ledger containing the Complete Works of Shakespeare, hidden among the many entries.

Blockchain requires more than just unique hashes for each block *individually*: each subsequent block on the chain must be indisputably connected to whatever came before it. So, how can you ensure that any change in this historical record will affect everything that follows it?

In fact, that's surprisingly simple:

<!--

INSERT TABLE2 IMAGE

-->

If you compare the previous two tables, you'll see that only the *Romeo and Juliet* hash is the same: by adding the previous hash to the content of each new block, every subsequent hash that was generated is different. Block 2 effectively contains Block 1 as well; Block 3 contains Block 2, which contains Block 1; Block 4 contains 3, which contains 2, which contains 1… and so on.

This means any alteration of earlier content affects everything that follows: changing either the *order* of blocks or the *content* of blocks will fundamentally change all the hashes that follow. **It becomes impossible to revise the blockchain *without everyone noticing***.


## Strength in Numbers

This methodology is at the heart of blockchain. A network of 100 nodes which share the Shakespearean ledger form a self-correcting system. Any copy of the ledger that contains a change to the established data will be profoundly different from all the others. Without a single authoritative node to dictate the truth, *majority rule* applies: the 99 nodes are dominant, and the 1 node that claims *Macbeth* came before *Hamlet* can be rejected and corrected to match the rest.

Not only does this mean that accidental errors are easily repaired, any deliberately malicious actions become extremely difficult to succeed. To sabotage the network (or, perhaps, just to change one money transfer so millions of dollars arrive in your bank account) you would need a majority of nodes to agree that your fake version of history is true. By distributing these necessary targets to unknown points across the internet, and in a geographical sense probably around the world, this kind of trickery would appear to be all but impossible.


## Further Learning

* ???
* ???


## Next up

At this point, a technical foundation for creating a trustworthy chain of blocks seems clear, as are some of the benefits of distributing them around a network. What isn't yet obvious is how to decide what content goes into each new block – after all, in a complex network new transactions will be occurring all the time, between different groups of participants. 

[The next section](ADD LINK HERE) explores how a single record of all this activity is collected, shared, and recognized by the entire network, and the role "dominance" plays in establishing a factual historical record.
