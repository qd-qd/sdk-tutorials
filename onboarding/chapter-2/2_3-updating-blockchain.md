---
title: "Updating the Blockchain"
order: 4
description: Network updates viewed from the node-level
tag: fast-track
---

# Updating the Blockchain

Previous sections have explored some of the mechanics of how blocks are created, explaining the value of hashing and the necessity of the nonce. Now it is time to switch focus from the big picture to the small scale.

_How can a node know for sure that the transaction history being spread across the network represents the absolute facts? Could there be, as politicians have been known to claim, "alternate" facts?_

<HighlightBox type="learning">

This section will cover:

* Proof or belief?
* Updating the blockchain
* Subverting a blockchain
* Defeating a 51% attack

</HighlightBox>

## Proof or belief?

It is easy to look at blockchain technology from a high and distant point of view and make assumptions or assertions about how it all works. *A distributed ledger, whose canonical history is updated by consensus reached between many equal network nodes, and which self-corrects against faults, errors, contradictory timelines, or orchestrated attacks* – that is accurate as an overview, but it obscures any detail of the activities at the node-level.

For example: imagine a network of 100 nodes in which one node's copy of the ledger differs from those of the rest. To the omniscient observer, it seems obvious that the minority case should be discarded in favor of the 99. However, that is *also* the situation when a new nonce is discovered and one lucky miner extends the chain, so "being in the majority" isn't automatically an assertion of authoritative status. Lesser majorities may inspire even less confidence – and what is the experience of a single node on the border between two (or more) competing claims about the ledger's history?

It is usually more accurate to think of differences arising in the blockchain as **matters of opinion**, not that some nodes are "correct" while others are "wrong". 

<HighlightBox type="note">

Whenever a new block is successfully mined, it represents a truthful statement about the information it contains, which includes the history of the chain. If two different miners create valid blocks at the same time, *both of their claims about the historical record are true* – they just make slightly different *but still true* claims about how that history can be extended.

</HighlightBox>

Even small differences between competing new blocks can make a large difference overall. Two blocks containing the same transactions but in different sequence can lead to the chain splitting into different versions of “the truth”. So, which truth should a by-standing node accept to resolve this conundrum?

## Updating the blockchain

For Proof-of-Work (PoW) networks such as **Bitcoin**, the decision about whether to accept a proposed extension to the blockchain (adding a block to the chain) is very simple: because the effort that goes into discovering a valid nonce is considered a measure of the difficulty that has been overcome, longer chains are seen as more valuable than shorter chains because more nonces needed to be identified to create them. Therefore, nodes in a PoW network adopt the longest available chain as canonical, and rapid hash checking allows the node to confirm the validity of its sequence of blocks with enough efficiency to enable network activity to continue uninterrupted.

If a node only has a single connection to the network, its knowledge of the wider state of the blockchain is severely limited. Any computationally valid update longer than the version it currently has will be immediately accepted, meaning its copy of the blockchain is only as reliable as that of its connection. However, even nodes with a healthy array of network connections are unlikely to find themselves torn between options for more time than it takes to confirm the validity of the longest chain.

You could visualize rival blockchain updates propagating through the network like waves, expanding outward from the successful miner nodes. Each connecting node compares the proposed extension with its existing ledger and updates itself to match. At nodes where the waves come into direct contact, the shorter chain falters and the longer chain continues unstoppably, sweeping over the rest of the network until consensus is regained.

### Making use of wasted work

As mentioned in [the previous section](ADD LINK HERE), there is a potentially concerning implication of this validation approach relating to cost and waste. The competitive nature of PoW networks is effectively "required", as it embodies blockchain's celebrated *no authorities* philosophy. However, this means that vastly more nodes engage in the mining process than the single node that wins the contest.

Each of these nodes represents a hardware and software resource demanding significant energy usage. A major part of the bad press often directed at cryptocurrencies and blockchain, in general, takes exactly this line, decrying the drain on public energy infrastructure. This seems all the worse when you consider that, technically, the majority of the work is discarded as worthless, even if it does contribute to the security of the network as a whole.

<HighlightBox type="tip">

For more information about how network scale relates to network security, see the coming section on the 51% Attack.

</HighlightBox>

Not all blockchain systems are quite so absolute, though, and different strategies create different opportunities. Whereas Bitcoin employs a long "block time" averaging 10 minutes, **Ethereum** uses a fraction of that, around 15 seconds. Shorter block times increase the chance that, due to network latency, nodes will unwittingly attempt to generate new blocks not based on the definitive longest chain – at first glance, another form of inefficiency.

Ethereum finds a way to put this apparently wasted effort to use. Valid blocks on chains that prove not to become canonical can be added alongside the winning block as its so-called "uncles", preserving work done across the network and increasing the total difficulty of the chain, which makes manipulation of the network much harder – more on this subject to come. 

By rewarding the miners of uncle blocks for their contribution to the blockchain's security (if to a lesser degree than the actual winning miner), Ethereum encourages mining participation more broadly than an all-or-nothing system. This helps discourage miner centralization.

![Uncles and the main chain](/onboarding/chapter-2/images/uncles.png)

Differences aside, the systemic value given to the longest chain and the vast computational effort required to identify the nonce and append each new block is a powerful combination – not just as a methodology for updating the network, but also for defending it against malicious intent. As is often the case, with blockchain *strength in numbers* is vital.

## Subverting a blockchain

To fully understand the strengths of a decentralized, distributed network, it is instructive to examine what would be required to undermine a blockchain-based system. Also to understand what could be gained from attempting to do so.

As was explained in [the previous chapter](ADD LINK HERE), blockchain is an answer to the *double-spending problem*. In effect, the objective of anyone attacking a blockchain is to successfully double-spend: to commit value to one or more transactions and gain some benefit, but then change the historical record to remove all the evidence of the spend so they can commit that same value a second time.

To succeed, the attackers must deceive a healthy, active network about the historical state of its shared ledger. The only way to achieve this goal is to create an alternative history that omits any transaction for which they want to double-spend the value. They must also beat a constantly ticking clock: competitive miners regularly extend the existing chain as new blocks of transactions are added, so any attackers are effectively in competition with all legitimate miners simultaneously.

### How to undermine a functioning consensus

Network nodes default to the longest chain when presented with competing alternatives. This means any plan to double-spend will require the attackers to create a fraudulent blockchain longer than the legitimate one – but it must still be computationally valid, or it will be rejected by nodes automatically. Therefore, the attackers' presence on the network must have more processing power than all the other miners *combined*.

Subverting a PoW validation system demands control of a *simple majority* (51%) of the network's computational power, allowing the attackers to on average reliably generate blocks faster than any other actor in the system. There is always the possibility of someone else finding a valid nonce with a lucky fast guess; however, since the generation of a valid nonce is random, statistically speaking even the slightest majority would result in network dominance in the long run.

This strategy is known as a **51% attack**.

### Conducting a 51% attack

A 51% attack would proceed as follows:

1. The attackers (most likely an alliance of network nodes) begin secretly mining blocks on an alternate blockchain, which runs parallel to the legitimate chain. Instead of submitting successful blocks when they identify a nonce, they allow the legitimate chain to continue working, completely unaware of what the attacker is doing.
2. The attackers perform a series of transactions *on the legitimate chain* using the value they plan to double spend, thereby gaining benefit. Simultaneously, they continue mining operations on the secret chain, *where they make no record of these transactions*.
3. Due to the attackers' superior computational power, their secret fraudulent chain grows faster than the legitimate chain being produced by the rest of the network. When it reaches such a point, the attackers are ready to launch the attack.
4. The attackers finally announce their fraudulent chain to the rest of the network. Because it satisfies the criteria of being the longer chain, the honest nodes accept it as correct and the network updates to match – *this erases the evidence of the attackers' earlier spending from the ledger*, but any benefit the attackers gained from those transactions is unaffected.
5. The attackers are now free to spend their value again, thereby cheating the system.

## Defeating a 51% attack

This kind of behavior is not to be supported. Fortunately, the scale of the task involved usually makes it impractical, though not always.

### The scale of the problem

Smaller blockchains are more susceptible to a 51% attack, but the bigger a PoW network is the less viable this strategy proves. As networks scale up and technology advances, the amount of computational power available increases. As a result, the difficulty posed by the creation of each nonce is deliberately raised to maintain a consistent rate of block creation.

Bad actors thus face an escalation of the challenge, demanding ever greater resources if they are to achieve the majority necessary to strike. In addition, there are the practical resources required: processing power and the energy to run it are expensive, and the up-front financial costs of undertaking a 51% attack can be considerable. It has been estimated that the cost of attacking Bitcoin through such an attack would rise into the *billions* of dollars – though Bitcoin likely enjoys the magical status of being "too big to fail", in this sense at least.

### Counter considerations

It is worth pointing out that there is a way for the owner of considerable computing muscle to benefit from participation in a blockchain that *does not* require acts of theft and deceit: just by engaging with the legitimate mining process, a powerful participant can earn real gains.

There is a more direct way to prevent this kind of undermining of a blockchain: *do not rely on Proof-of-Work to achieve consensus*. As [mentioned previously](ADD LINK HERE), Proof-of-Authority limits who can define the state of the blockchain, and Proof-of-Stake also bakes in penalties for misbehavior, while Delegated-Proof-of-Stake adds the ability for nodes to oust troublemakers as well.

These methodologies may not be immune from manipulation, since they rely on elevating participants to positions of power where they can conceivably act against the common good - and arguably the 51% attack itself is an abuse of *assumed* authority, embodying a functional domination of the system. However, they do rule out mystery miscreants striking and disappearing into the shadows.

## Further learning

* ???
* ???

## Next Up

The [next section](ADD LINK HERE) will address two key concerns that may seem highly significant in the context of a shared ledger: privacy and confidentiality.
