---
title: "Blockchain Use Cases"
order: 6
description: Types of network, types of application
tag: fast-track
---

# Blockchain Use Cases

Now it is time to consider some practical applications of blockchain. Some people claim blockchain technology has the potential to change the world for the better – is there any evidence of this already?

<HighlightBox type="learning">

This section will cover:

* Public networks
* Private or "managed" networks
* Real-world use cases

</HighlightBox>

## Blockchain categorization

There are various use cases for blockchain that do not necessarily revolve directly around the transfer of monetary value. Some of these are already implemented, others are yet to surface. Before you look at some specific cases, it is important to define two broad categories blockchains can be divided into: **public** networks, and **private** (or **managed**) networks.

### Public networks

Public networks are implemented in the way blockchain technology was originally intended to. Cryptocurrencies and other tokenization projects are the most obvious examples. These are some key specific attributes that public blockchains generally share:

* **Accessibility:** participation is open to anyone with the necessary client software and an internet connection – and anonymity is acceptable, if not actually systemic.
* **Absence of hierarchy:** all nodes are equal and all validators are equal.
* **Decentralization:** many public networks are completely decentralized - this may not work well with traditional business models.
* **Crypto-economic incentives:** without an absolute defense against malicious action, benevolence is reinforced via rewards which, in combination with often significant network scale, disincentivize behavior that might endanger network function.

<HighlightBox type="info">

Historically, public networks have been synonymous with the Proof-of-Work (PoW) consensus model, which underpinned Bitcoin and the many blockchain-based projects which followed it. However, the monopoly of this approach is now challenged by a variety of alternative methodologies, [as will be discussed in a later section](ADD LINK TO CH2-SEC2).

The significance of network scale in protecting blockchains against bad actors [will also be explored later](ADD LINK TO CH2-SEC3).

</HighlightBox>

### Managed networks

Private or "managed" networks also rely on blockchain data structures. However, while solving misbehaving nodes is always important for a stable network, in managed networks Byzantine Fault Tolerance (BFT) is less of a critical factor to be solved. A public network encourages an emergent, anonymous hierarchy to temporarily arise within an unpredictable ecosystem. Managed networks, on the other hand, are predictable environments that maintain some traditional elements of authority and accountability.

Managed networks also differ from public ones in that they retain the necessity for some degree of trust, so their most logical use cases are where trust already exists between the participants. A hypothetical example might be a network between financial institutions used to settle inter-bank transactions, for which public access would be not just unnecessary but undesirable. Each institution could operate one validator and no single node would be able to corrupt the network's ledger. However, if systemic revisions to the history were required, such work would represent a coordinated action by a small number of known, trusted actors.

Managed networks likely seek certainty that pending transactions will be included in the next block, and guarantees of network integrity, which the probabilistic nature of public blockchain networks cannot promise absolutely. Nevertheless, blockchain technology offers promising solutions to various concerns faced by a range of institutions. The challenge lies in identifying how to take advantage of its strengths.

Managed networks may use blockchain as a way of perpetuating pre-existing relationships, or automating processes. They can be:

* **Designed for limited numbers of vetted and approved participants:** performance challenges and poorly connected nodes are less important.
* **Designed for optimized performance:** participants in an enterprise network can typically run powerful, well-connected, high availability nodes.
* **Governed by well-defined agreements:** decision-making matters such as protocol upgrades, admission requirements, and remedial actions may be codified in advance.

## Real-world use cases

The most obvious examples of blockchain in action are *cryptocurrencies* and *non-fungible tokens* (NFTs), which in recent years have become familiar terms in the global discourse surrounding blockchain.

<ExpansionPanel title="Cryptocurrencies and NFTs">

Most people are already familiar with these applications, but click the following expansion panels for a brief overview of each one.

**Cryptocurrency**, casually referred to as "crypto", is *a digital form of currency that is not dependent on any central authority*, such as a government or bank. Bitcoin was originally conceived to help explain the features of blockchain as a software tool, but went on to become the first actual cryptocurrency and remains the most valuable example to this day.

Alternative cryptocurrencies were originally based on copies or modifications of the Bitcoin code, a difficult undertaking. **Cosmos** allows developers to create new blockchains for many purposes, including cryptocurrencies, with far greater ease.

A **non-fungible token** is *a tradeable digital asset* (such as an image file), and any transfer of ownership is proven by the immutable blockchain ledger. Unlike the units of a cryptocurrency, NFTs are individually unique, which is the basis of their value.

However, there is debate over the extent to which the sale of an NFT represents a legal transfer of rights or ownership over the associated digit asset. In practice, the trading of an NFT technically only represents a change in ownership of the NFT itself and not necessarily that of the asset, which typically is stored conventionally and referenced on the blockchain only by a URL. It is difficult to prevent anyone from accessing the target of the URL and creating a different NFT for the same asset or even duplicating the original file entirely.

<HighlightBox type="tip">

The difference between cryptocurrencies and NFTs is that strange word, **fungible**. If something is fungible, it is fundamentally interchangeable with another example of itself. Two cans of a particular brand of dog food are fungible, but two dogs are not, even if they are of the same breed – any pet owner will assure you that their dog is unique, and nobody ever swaps pets. 

As well as uniqueness, **non-fungibility** also indicates that a thing *cannot be broken down into smaller divisions of itself*. The contents of a can of dog food can be divided into multiple portions without losing value – it arguably becomes *more* useful, allowing you to control the expenditure of that value over time. Two halves of a dog, by contrast, are worth less than the sum of their parts.

Bitcoins are much like any other unit of currency: if you exchange one $20 bill for two $10 bills, your wealth remains unchanged, and similarly you can make a transaction of 0.5 Bitcoins, for example. Both dollars and cryptocurrnecy tokens are *fungible*. 

NFTs, as their full name suggests, are *non*-fungible tokens: their worth lies in relation to some unique property (at least in theory), and ownership of the whole NFT is traded for actual financial value.

To summarize:

* **Fungible tokens** are non-unique and divisible.
* **Non-fungible tokens** are unique and indivisible.

</HighlightBox>

</ExpansionPanel>

However, there is a lot more to blockchain than just these high-profile and often divisive examples. There are already more varied blockchain applications implemented today than can be easily summarized. The following use cases look at a few specific fields in detail to illustrate how blockchain technology can be leveraged in different contexts.

### Governmental services

The first thing everyone associates with "government" is bureaucracy: endless red tape, challenges and failures of communication, the laborious duplication or unhelpful separation of data between (or even within) departments, and the expenses this costs taxpayers and private entities like companies.

All of this can be countered through blockchain implementations. A unified, distributed public data resource could be made broadly accessible to a network of authorized government institutions and agencies while being secured against misuse or destruction, with any revisions to a citizen's records becoming immediately available for use across the system.

One fledgling example of this is the [National Digital ID (NDID)](https://www.ndid.co.th/), a public-private collaboration to provide citizens of Thailand with a unified online identification that facilitates banking, credit, insurance, tax reporting, healthcare, and educational activities for millions of end users through a single, highly secure blockchain-based system.

### Healthcare information

Blockchain applications can also deliver parallel but important-to-differentiate services relating to patient information. A person's medical history is, of course, potentially vital to their future, yet sharing information between healthcare institutions is notoriously difficult to manage. Simultaneously the raw data generated by patients as a whole can be invaluable, such as to ongoing scientific research, but protecting the privacy of individual patients is essential.

[HealthVerity](https://healthverity.com/) provides such services by using blockchain technology to restrict access permission to confidential data even as it is put to work for both the patient and interested third parties in approved, anonymized forms. [HashedHealth](https://hashedhealth.com/), which has spawned various blockchain-based platforms, is also developing a system to confirm the credentials of medical practitioners in the United States of America to prevent unlicensed activities in particular states.

There are blockchain-based projects related to vaccine administration and tracking, and it has also been used in the genomics industry. While genomics is not directly a medical-focused field, the demands of personal data privacy are well-matched to blockchain's decentralized security.

### Vehicle manufacture and maintenance

The use of blockchain as a valuable tool for supply chains is now well-established, but it is worth underlining just how beneficial it can be, especially in contexts where human safety is a key concern, like vehicle manufacture, repair, and maintenance.

The ability to reliably track the provenance of components, and even identify the specific vehicles in which they are used, can impede the introduction of counterfeit parts or allow for precision targeting of unit recalls if a component is found to be faulty. This significantly reduces costs to the manufacturer and removes inconvenience to car owners who could be wrongly identified as needing maintenance because their particular vehicle does not contain an affected component. The [Mobility Open Blockchain Initiative](https://dlt.mobi/) aims to deliver whole-life vehicle records including complete maintenance histories and listing regional registrations.

Private ownership is not the only context of course. In the airline industry, the tracking and tracing of parts is traditionally a largely manual administrative process open to costs, delays, and human error. Blockchain has been estimated to potentially save billions through improved efficiencies and the full digitalization of maintenance records could lead to further benefits such as predictive maintenance, as well as reducing aircraft downtime and accidents.

Aerospace and defense interests at both the corporate and state level are also exploring blockchain technology to streamline the tracking and retail of valuable components.

### Transportation and travel

Moving away from purely mechanical issues, other travel industries are implementing blockchain projects in numerous ways: decentralized ride-hailing services, in which independent drivers are not beholden to a central business; tracking the use of public transport systems like buses and "bike shares" to improve services; securing and coordinating the range of personal data that airline travelers need to manage, such as personal and passport data, payment details, immigration or border permissions, and now vaccination status. Smart contracts can also impact ticket purchases by delivering smoother booking processes.

The transportation of goods demands a great deal of information transfer, whether the supply chains in question are local, national, or global, so blockchain can have useful applications here. The [Blockchain In Transport Alliance (BiTA)](https://www.bita.studio/) identifies the technology as a way to improve transactions, shipment tracking, fleet management, and efficiency in the trucking and freight industries.

Vehicle purchase or leasing can also be impacted, with blockchain offering iron-clad records of ownership or use, accident data, and insurance records. For example, the Estonian company [carVertical](https://www.carvertical.com/) uses a blockchain-based criteria search service for people interested in buying second-hand cars.

### Publishing and the press

The concentration of power in publishing has been long criticized by observers, with the long-established "Big Five" forever absorbing smaller publishers and narrowing opportunities for less-established authors. Digital disruption of these so-called "gatekeepers" by Amazon and its rivals has led to accusations of market monopolization, and questionable practices towards publishers and individual authors alike. All this makes publishing a field ripe for innovative ways to connect readers with the written word.

The Canadian platform [Bookchain](https://www.bookchain.ca/) applies blockchain technology to various aspects of digital publishing, offering authors new ways of distributing their work with indisputable proof of attribution, protection against illegal copying or transfers, and even allowing them to track the ongoing ownership of their ebooks should buyers legitimately sell them on.

Fact as well as fiction can benefit. As an immutable historical record, blockchain can have implications for news reporting, the context of how material is published, and how it is subsequently referenced. [The News Provenance Project](https://www.newsprovenanceproject.com/) and [Content Authenticity Initiative](https://contentauthenticity.org/), both in association with *The New York Times*, use blockchain features to fight misinformation or misuse by tracking how material is used and referred to, or identifying if it is manipulated.

Blockchain can also work against censorship, in that any content on a chain becomes almost impossible to modify or erase – provided the chain itself remains accessible of course.

## Scratching the surface of blockchain possibilities

The previous examples were chosen to demonstrate the great variety of industries that blockchain could impact, but there are many more. The technology has already been applied to corporate governance and business forecasting; telecommunications and "the Internet of Things" (IoT); energy and waste management; commercial industries like construction, real estate, entertainment media, e-commerce, and retail; and resource management industries such as farming, fishing, logging, and mining – the list goes on.

Directly or indirectly, the work you do in your role contributes to this ever-expanding culture of blockchain-based solutions to different activities around the world, both large and small.

## Further learning

<HighlightBox type="learning">

* For an extended breakdown of blockchain use cases, including those mentioned here, see the comprehensive article [Banking is only the beginning](https://www.cbinsights.com/research/industries-disrupted-blockchain/), at *CBInsights.com*.
* For a quick video overview of blockchains in the medical field, watch [3 Ways How Blockchain Will Change healthcare](https://www.youtube.com/watch?v=Oga9J0NFwAA) by The Medical Futurist.
* You can find a full list of application projects built on the Cosmos Ecosystem [here](https://cosmos.network/ecosystem/apps/).

</HighlightBox>

## Next up

This concludes Chapter 1 of the Onboarding Course! It has provided a wide-ranging, general overview of blockchain technology, its place in the workplace, and its potential impact on the world. The next chapter will build on this by looking at the specific mechanisms of how blockchain works, with accessible and intuitive examples at every stage.

Before you continue to Chapter 2, it is recommended to take a look at [the Chapter 1 Resource Bank](ADD LINK HERE). Then you can take a short [self-assessment test](ADD LINK HERE) to see how comfortable you are with the information you've received so far.
