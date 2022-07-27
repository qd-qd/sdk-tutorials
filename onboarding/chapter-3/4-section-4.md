---
title: "Smart Contracts"
order: 5
description: Exploring a new version of a familiar concept in more detail 
tag: deep-dive
---

# Smart Contracts

Back in Chapter 1 you looked at the basics of **Smart Contracts** in the context of [working in the blockchain era](ADD LINK HERE). Now it is time to dive deeper into their nature.

<HighlightBox type="learning"> 

This section will cover:

* What is a smart contract?
* Smart contract history
* Theoretical and practical understanding
* Smart contracts in the blockchain context
* Pros and cons of smart contracts

</HighlightBox>

A contract is commonly known as a *formalization of a relationship and/or transaction*. In common law a contract is understood as a "meeting of minds" – which entails an intricate play of trust-building and relies on a legal system evolved over centuries with deep underlying traditions and understandings.

**Smart contracts are not equal to contracts in the realm of traditional, non-digital law**. It is essential to differentiate smart contracts from existing contract forms, and to be mindful of this to avoid unintended consequences and the transfer of misconceptions.

**Trust mechanisms** in traditional contract law are based on human agents, institutions with authority to enforce contracts, and the concept of intent. Smart contracts by contrast operate on trust mechanisms based on their source code, and rely on signaling transparency. Smart contracts, even if part of the digital world, are not free from public constraints, as well as under the influence of economic and societal norms.

## What is a smart contract?

Essentially, smart contracts are automated agreements between contract creators and recipients, *written in code*. They are baked into blockchains that exist across distributed, decentralized networks – meaning **smart contracts are immutable and irreversible**. These contracts allow for the execution, enforcement, and verification of agreements among anonymous parties, without needing a central authority, legal system, or external enforcement system.

Virtual-machine blockchains like Ethereum addressed the demand for more programmability because, at the time, the options available for building decentralized applications (dApps) were limited. Before Ethereum introduced smart contracts, most developers would build on top of the complex and limited Bitcoin scripting language or fork the Bitcoin codebase, which was hard to work with and customize. The Ethereum Virtual Machine (EVM) brought the possibility of interpreting Turing-complete programs, smart contracts, which were suited for use cases like one-time events such as initial coin offerings (ICOs).

Smart contracts are a main application area in blockchain technology. Understanding what a smart contract is and how it can be deployed (as well as knowing what important aspects to keep in mind when developing and deploying a smart contract) is key to understanding blockchain technology's possible areas of application and current developments in the field.

## Smart contract history

Nick Szabo first used the term **smart contract** in the 1990's in his paper [Formalizing and Securing Relationships on Public Networks](https://journals.uic.edu/ojs/index.php/fm/article/view/548/469), introducing the possibility of efficiently transferring automated traditional contracts from common law into distributed protocols, especially in conjunction with digital transactions. 

<HighlightBox type="Info">

Szabo used the example of a vending machine to break his proposition down into a real-life scenario. A vending machine is a contract with a bearer: those with a sufficient amount of coins can engage in an exchange and receive the goods offered, *without the need for an actual person to take the money and hand over the item*. 

Smart contracts in blockchain serve that same purpose, but are much more versatile.

</HighlightBox>

Szabo envisioned a world where contracts could be embedded in all kinds of property with value and be controlled digitally. The main argument is that software could minimize human involvement, therefore lowering costs and creating a more efficient relationships by automating contract performance, monitoring, and enforcement. This is where the "smart" comes in: these type of contracts are "self-enforcing".

Since Szabo's article, we use the term "smart contract" to describe *a transaction protocol executing the terms of a contract as understood in common law*. It can be understood as a legally binding contract in digital form.

In 1998, Szabo proposed a digital currency called Bit Gold. While the asset was never actually launched, this Bitcoin predecessor argued for using smart contracts to conduct trustless transactions online.

Smart contracts later resurfaced with the rise of **distributed ledger technology** (DLT), which revitalized the debate surrounding their advantages and usefulness, as well as the potential applications of smart contracts.

## Theoretical and practical understanding

The term smart contract is often misused or misunderstood. They can be viewed either from a theoretical perspective (essentially differentiating them from the conventional notion of a contract) or more practically in the context of the Ethereum protocol.

When looking at the concept of smart contracts in the **Ethereum protocol**, the focus is on the application. Code storing and execution is possible on Ethereum's distributed ledger network, and smart contracts in Ethereum partially achieve what Szabo envisioned, as one can transfer and hold funds to secure and enforce predefined transactions and relationships. The contract itself contains the enforcement of its terms, as the execution of the agreement is clear at the moment it is deployed. This leads to third parties playing a much smaller role. 

Smart contract advocates expect that by automating contracting, human error is eliminated and lower error rates can be expected. Intermediaries are expected to pay a secondary role in the future; it is often argued that they would only come into play when addressing performance evaluation and in dispute resolution. For now, smart contracts are mainly used in making fund transfers possible through the blockchain, but they could be used for any processes in which a reliable record is necessary.

## Smart contracts in the blockchain context

A **smart contract** represents *a computer protocol intended to provide a self-executing, self-enforcing, and self-verifying contract.* As such, smart contracts allow developers to write custom logic on blockchains.

From a programming standpoint, a smart contract is a coded **"if/when…then"** statement, executed when a trigger condition is fulfilled – that is, as soon as pre-determined terms and conditions are met. You can understand them as automated agreements. Due to their automation, the need to resolve disputes through legal means is expected to be reduced.

### The Virtual Machine environment

Smart contracts are account holding objects that contain code functions, usually deployed on blockchains that have a virtual machine (VM) as part of their application layer. Developers are limited to the specific programming language of the VM in question, and can only choose from a limited set of functions for their cryptographic operations.

As all smart contracts on a given VM are run by that single machine, they share the same underlying environment and compete for resources. This can severely restrain performance. Even if the state machine is able to split in multiple subsets, for example with sharding, the contracts still need to be interpreted by a VM, which would limit performance.

### Smart contracts are self-executing

Smart contracts automate established "contractual" terms, as specified in the code. As soon as the terms and conditions are met, the code of the smart contract is executed. This does not require the developer to set any type of flag or have any type of further interaction with the smart contract – it is coded in such a way that it can run and execute its operations independently. For this reason, smart contracts are viewed as self-executing.

The process of forming self-executing contracts is facilitated through the use of protocols and user interfaces. As they operate in the realm of blockchain networks, the triggers a smart contract responds to and the actions it executes are conducted through transactions.

### Smart contracts are self-enforcing

Since smart contracts are coded to be self-executing, they also contain the enforcement of their terms: the stipulated actions are automated and therefore self-enforcing. However, 
this means that any unintended outcomes permitted by the coding may be non-trivial.

Like other forms of software, smart contracts do precisely what they are programmed to do. This can stand in stark contrast to what the author of a contract intended. Smart contracts do not include the concept of intent or context, so they require that contingencies and outcomes are specified in great detail to ensure proper functioning, as well as to prevent unintended consequences. In a common law setting, any disputes of this sort would be settled in court. 

Smart contracts cannot be changed once deployed, as immutability in blockchain networks also holds for smart contracts. This makes the self-enforcing stipulations transparent but can also lead to potential risks: once a contract is deployed and the trigger is met, the code is executed without the possibility of interference – even by the contract's author. Disputes made at his juncture may well be considered "too little too late".

### Smart contracts are self-verifying

Since smart contracts exist on the blockchain, as soon as the contract terms are met transactions are automatically carried out; data is recorded securely, and cannot be altered nor deleted. Thus, there is no need for verification outside the contract – assuming the code leads to no unintended consequences.

The smart contract itself can verify proper execution with the conditions specified, because all actions are conducted in form of transactions, which are traceable and permanent. In the end, the immutability of blockchain networks combined with the automation of a deployed smart contract make them self-verifying.

## Pros and cons of smart contracts

Now that you have a solid understanding of what a smart contract is, a closer look at the benefits and potential disadvantages of smart contracts is advisable.

### Strengths

Once a triggering condition is met, a smart contract immediately begins executing. This makes smart contracts **faster, more efficient, and more accurate** compared to partly-automated or completely manual processes. The potential for error due to manual data and document handling is eliminated.

In comparison with common law contracts, smart contracts are more **time-efficient**. They do not have to go through the different stages of contracting, which include intermediaries and are determined by the legal framework that applies. Smart contracts are often viewed as an opportunity to bypass the legacy of centralized inefficiencies.

The potential for automation combined with the reduced need for intermediaries results in **cost-effectiveness**. Involving intermediaries does not only increase the amount of time a process requires but potentially raises the costs for that process to be conducted, due to additional fees, for example. The reduced role of intermediaries translates to lower fixed costs and fees, as well as faster transaction times.

As smart contracts are deployed in blockchain networks and all transactions on the network are recorded in a immutable, tamper-proof, and transparent shared ledger, this leads to **increased trust** in the contract itself. Contract compliance and enforcement are completely independent of any third parties and ruled by the smart contract code.

Smart contracts are **secure** because the blockchain's ledger is encrypted and all records are interconnected cryptographically to establish immutability. A malicious participant would have to alter the entire chain to change a single detail on the ledger and then get the new version successfully approved through the validation consensus. Tampering with a single element of a single smart contract would demand tampering with the entire blockchain.

A smart contract is **more flexible** compared to a common law contract because they do not have to be compliant to a legal framework - one could opt for legal compliance, but one does not have to.

Unlike common law contracts, smart contracts are not subject to interpretation and exist without context. As long as the contract is coded taking into account unintended consequences and with an eye to detail when it comes to potential loopholes, the **potential of a deviating contract implementation is minimized**.

### Weaknesses

Characteristics that make smart contracts attractive can at the same time can also be seen as causing shortcomings. Blockchain's immutability and the smart contract's self-execution makes it **impossible to change** the process case-by-case. Thus, before implementing a smart contract's code, developers should think about the following questions:

* What is the general process flow that will be implemented by the code?
* What is the trigger to start execution?
* How is the execution enforced by the code?
* What conditions need to be met to verify proper functioning?
* What are potential unintended consequences? And how could they be mitigated?
* Are there any loopholes that could be exploited?

**Human error** might not be an issue in regard to execution, but it could be a critical factor when the code is being written. Errors in the code could lead to the contract wrongly executing or containing loopholes open to exploitation by malicious nodes. Correcting errors can be costly, requiring the code to be reoptimized and redeployed to the chain, as most protocols do not have a mechanism to update a smart contract.

Another disadvantage of relying completely on smart contracts relates to **regulatory clarity**. Legal uncertainty is an issue in many use cases when it comes to blockchain technology. Although regulatory agencies and institutions have worked on adapting to the changed technological landscape of the 21st century, there is still a lot of gray area. **Smart contracts are not legally-binding contracts**: they can *represent* a contractual relationship, but are not one per se. 

When it comes to transactions of cryptocurrencies and tokens holding value, general regulation has also been a pressing issue, especially regarding taxation. This means **any type of litigation can be difficult**. It can only be assumed that regulatory clarity will be achieved in time, as the technology is still maturing and so is the legal framework.

Smart contracts have **limited functionality and awareness**. They exist in a blockchain universe, therefore they can only base their execution on the information and data included on-chain. **For any external data or information, an oracle is needed**.

<HighlightBox type="info">

Similar to how an oracle in ancient times provided insights and counsel based on its predictions, **an oracle** in blockchain is *a third-party service providing information to smart contracts and other on-chain mechanisms from outside the blockchain*. Oracles can also be used to provide off-chain services with information *from* the chain.

<ExpansionPanel title="Considerations regarding oracles">

Relying on an oracle can be problematic, as the quality of data and reliability is determined by the oracle. If you pick the wrong oracle, you might end up with faulty or even maliciously deceptive data. This holds especially for oracles based on a single source of truth. 

As with centralization in general, such a single source of truth could be attacked or altered by those managing the data source. Thus, using a decentralized oracle that queries multiple data sources, helps counter the issue of potentially unreliable data.

In addition, because oracles are not part of blockchain networks but external to them, the information provided is not part of the blockchain's consensus and does not benefit from the security architecture of blockchains.

</ExpansionPanel>

</HighlightBox>

Finally, a persistent challenge in blockchain environments remains **scalability**. Sometimes adding more machines to a network is done to counter scalability issues. More machines means more nodes can be accepted and then participate in state replication and consensus, but this only helps counter the issue to a certain point.

The amount of resources available for smart contract execution are limited to the network the contract is running on. All operations in a blockchain that are to be conducted share the network's pooled resources. This can lead to very tight competition after a certain network size is reached. 

The scalability issue is one of the main pressure points Cosmos envisioned to address. You will learn more about the benefits Cosmos provides in this regard during [Chapter 4](ADD LINK HERE).

## Further learning

* ?????
* ?????

## Next up

In the [final section](ADD LINK HERE) of this chapter, you dive deeper into cryptocurrency and crypto economics.
