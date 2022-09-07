<!--
layout: LandingPage
intro:
  - title: Interchain Developer Academy
    image: /graphics-sdk-course.png
    description: |
      Welcome to the Interchain Developer Academy! <br/>
      In the next 6 weeks, you'll dive deep into the Cosmos ecosystem. Let's get started!
    action: 
      label: Start course
      url: /#overview
    secondtext: |
      This is a beta version of the Developer Portal that will help you take your first steps with the Cosmos SDK.
      <br>We would be grateful for your feedback. At the end of each are three icons to rate the page and a small box where you can give us feedback about things to improve. Enjoy your journey through the portal and good luck with the HackAtom!
overview:
  title: Important program information
  items:
    - title: Timeline and deadlines
      description: |
        This course offers an overview of the Cosmos SDK, as well as examples and exercises to help developers get a quick start.
    - title: What you'll learn
      description: |
        This course unfolds the Cosmos universe, beginning with a big picture perspective and getting into how to create your own application-specific blockchain with the Cosmos SDK.<br/>
        You can follow two tracks: The fast track and the deep dive. The fast track gives you a solid overview of the Cosmos SDK, its components, and dApps in Cosmos. The deep dive takes you through hands-on exercises to put theory into practice – showcasing how to address application concerns when developing such as managing gas fees and cross-chain communication, working with Ignite CLI, running a node, and understanding CosmWasm. All sections are tagged accordingly as “Fast track” or “Deep dive”. A look into all chapters is recommended as a basic understanding helps when things get tricky.
    - title: How to get the most out of the Academy
      description: |
        For the fast track, you should have a solid understanding of blockchain technology and be familiar with decentralized applications. The deep dives are specially designed for experienced developers.
    - title: How much time do I need to dedicate to the Academy?
      description: |
        With the fast-track, you will gain a solid understanding of Cosmos and its SDK. This might be a matter of just an hour or two. The time you spend on the deep dive depends on you – there are endless possibilities to discover. <br/><br/>
        Welcome to the cosmos!
    - title: What support will I get in the Academy?
      description: |
        With the fast-track, you will gain a solid understanding of Cosmos and its SDK. This might be a matter of just an hour or two. The time you spend on the deep dive depends on you – there are endless possibilities to discover. <br/><br/>
        Welcome to the cosmos!
    - title: How do I access Discord?
      description: |
        With the fast-track, you will gain a solid understanding of Cosmos and its SDK. This might be a matter of just an hour or two. The time you spend on the deep dive depends on you – there are endless possibilities to discover. <br/><br/>
        Welcome to the cosmos!
    - title: How do I get certified?
      description: |
        With the fast-track, you will gain a solid understanding of Cosmos and its SDK. This might be a matter of just an hour or two. The time you spend on the deep dive depends on you – there are endless possibilities to discover. <br/><br/>
        Welcome to the cosmos!
imageSection:
  title: Important Dates
  description:
  image: /ida-timeline.svg
modulesIntroduction:
  title: Weekly Plan
  description: |
    The Academy runs for 7 weeks. You can follow the weekly structure or decide to go your individual path - just make sure to be ready for the Final Exam after 7 weeks.
  sections:
    - image: /cosmos_dev_portal_module-02-lp.png
      title: Getting started
      description: |
        This chapter is completely optional and a good introduction if you are new to blockchain technology or need a refresher on:
      links: ['/academy/1-what-is-cosmos/blockchain-and-cosmos.html', '/academy/1-what-is-cosmos/cosmos-ecosystem.html', '/academy/1-what-is-cosmos/atom-staking.html']
    - image: /cosmos_dev_portal_module-03-lp.png
      title: Week 1 - Introduction to Cosmos
      description: |
        You'll discover the Cosmos ecosystem and learn about the main concepts of the Cosmos SDK, from its Tendermint consensus to learning how keys, accounts, and transactions relate to each other. Dive into:
      links: ['/academy/2-main-concepts/', '/academy/0.0-B9lab-Blockchains/2_public.html', '/academy/2-main-concepts/', '/academy/0.0-B9lab-Blockchains/2_public.html']
    - image: /cosmos_dev_portal_module-04-lp.png
      title: Week 2 - First Steps
      description: |
        You'll discover how to run a node and learn how to build your own chain by following an example implementation of a checkers blockchain. Discover:
      links: ['/academy/2-main-concepts/', '/academy/0.0-B9lab-Blockchains/2_public.html', '/academy/2-main-concepts/', '/academy/0.0-B9lab-Blockchains/2_public.html']
    - image: /cosmos_dev_portal_module-02-lp.png
      title: Week 3 - Introduction to IBC and CosmJS
      description: |
        You'll dive into IBC to learn more about cross-chain communication and how to use CosmJS for your chain in the following sections:
      links: ['/academy/1-what-is-cosmos/blockchain-and-cosmos.html', '/academy/1-what-is-cosmos/cosmos-ecosystem.html', '/academy/1-what-is-cosmos/atom-staking.html']
    - image: /cosmos_dev_portal_module-03-lp.png
      title: Week 4 - Ignite CLI and IBC Advanced
      description: |
        You'll dive deeper into customizing the checkers blockchain to make your game more interesting and unique with Ignite, while also testing  and expanding your IBC knowledge to:
      links: ['/academy/2-main-concepts/', '/academy/0.0-B9lab-Blockchains/2_public.html', '/academy/2-main-concepts/', '/academy/0.0-B9lab-Blockchains/2_public.html']
    - image: /cosmos_dev_portal_module-04-lp.png
      title: Week 5 - CosmJS Advanced
      description: |
        You'll build on your previous work with CosmJS to implement a sound game GUI and a backend script that improves the user experience by:
      links: ['/academy/2-main-concepts/', '/academy/0.0-B9lab-Blockchains/2_public.html', '/academy/2-main-concepts/', '/academy/0.0-B9lab-Blockchains/2_public.html']
    - image: /cosmos_dev_portal_module-02-lp.png
      title: Week 6 - IBC Advanced II
      description: |
        You'll further deepen your knowledge of IBC by looking into
      links: ['/academy/1-what-is-cosmos/blockchain-and-cosmos.html', '/academy/1-what-is-cosmos/cosmos-ecosystem.html', '/academy/1-what-is-cosmos/atom-staking.html']
    - image: /cosmos_dev_portal_module-03-lp.png
      title: Week 7 - Run in Production
      description: |
        You'll build on your previous work for the checkers blockchain to adapt your blockchain to the demands of running in production:
      links: ['/academy/2-main-concepts/', '/academy/0.0-B9lab-Blockchains/2_public.html', '/academy/2-main-concepts/', '/academy/0.0-B9lab-Blockchains/2_public.html']
tools:
  - title: Cosmos SDK
    description: A framework for building public blockchains.
    links:
      - name: Learn more
        url: https://v1.cosmos.network/sdk
      - name: Documentation
        url: https://docs.cosmos.network/
    image: /cosmos-sdk-icon.svg
  - title: Tendermint Core
    description: Blockchain consensus engine and application interface.
    links:
      - name: Learn more
        url: https://tendermint.com/core/
      - name: Documentation
        url: https://docs.tendermint.com/
    image: /tendermint-icon.svg
  - title: Ignite CLI
    description: All-in-one platform to build, launch, and maintain apps on a sovereign and secured blockchain.
    links:
      - name: Learn more
        url: https://ignite.com/cli
      - name: Documentation
        url: https://docs.ignite.com
    image: /ignitecli-icon.svg
  - title: IBC
    description: Industry standard protocol for inter-blockchain communication.
    links:
      - name: Learn more
        url: https://ibcprotocol.org/
      - name: Documentation
        url: https://ibc.cosmos.network/
    image: /ibc-icon.svg
  - title: CosmWasm
    description: Smart contracting platform built for Cosmos ecosystem.
    links:
      - name: Learn more
        url: https://cosmwasm.com/
      - name: Documentation
        url: https://docs.cosmwasm.com/docs/1.0/
    image: /cosmwasm-icon.svg
  - title: Cosmos Hub
    description: Software powering Cosmos Hub, the heart of the Cosmos network, and home of the ATOM token.
    links:
      - name: Documentation
        url: https://hub.cosmos.network/
    image: /generic-star-icon.svg
-->