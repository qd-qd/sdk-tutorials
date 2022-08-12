---
title: "Engaging With the Cosmos Ecosystem"
order: 6
description: A practical exercise in using Cosmos to learn about staking
tag: deep-dive
---

# Engaging With the Cosmos Ecosystem

The [Cosmos Hub](https://hub.cosmos.network) is the first among equals of Cosmos blockchains. ATOM is its native token, also called the staking token. You need some ATOM to be able to transact on the Cosmos Hub or to participate in the Proof-of-Stake (PoS) consensus.

<HighlightBox type="learning">

In this section you are going to:

1. Install a wallet application.
2. Get some ATOM.
3. Participate in the consensus to passively earn a yield on your ATOMs while working on your own Cosmos application, sleeping, or studying further.

</HighlightBox>

## Getting ATOM and staking it

There are two steps to successfully getting ATOM:

1. Install a wallet application and configure it safely.

<HighlightBox type="info">

You can find a step-by-step guide on how to use [Keplr](https://keplr.app/) further below.

</HighlightBox>

2. Buy some ATOM on an exchange and transfer them to your wallet.

## Setting up Keplr

Open Google Chrome on your computer and go to the [Keplr extension page](https://chrome.google.com/webstore/detail/keplr/dmkamcknogkgcdfhhbddcghachkejeap). Alternatively, you can search for Keplr in the [Chrome extensions store](https://chrome.google.com/webstore/search/Keplr).

<HighlightBox type="tip">

It is always good practice to be careful with links to wallet software because of the possibility of fraudulent software designed to steal from you. A link to the official Keplr extension can also be found on the [Cosmos Ecosystem overview page](https://cosmos.network/ecosystem/wallets).

</HighlightBox>

When installed, Kepler should be available in your list of extensions when you click on the icon that looks like a puzzle piece in the top-right corner of Chrome:

![Keplr seen as an extension in Google Chrome](/keplr-as-extension.png)

<HighlightBox type="warn">

When you own ATOM with Keplr, **you are in charge**. There is no one you can call if _you forget your password/seed phrase or you send tokens to the wrong address_.

**Keplr is a non-custodial wallet.**

</HighlightBox>

With the Keplr extension installed and the above warning in mind, create a new account. Click on your Keplr extension and the following page should open:

![Creating a new account or connecting to an existing account with Keplr](/keplr-create-menu.png)

Click _Create new account_. The page that opens offers you a mnemonic, which is a secret list of words and asks you for a password. Because **you are in charge**, it is important to understand the following points:

* Whoever knows the **mnemonic seed** has access to **all** the assets in the wallet as easily as you do. This means that:
    * Nobody else should be looking at your screen right now. If that is not the case, click _Back_.
    * You should save the mnemonic seed in a safe place so that you can import it back into this or another wallet at a later date. **Make sure** you write it down somewhere safe.

<HighlightBox type="warn">

You should only ever share your mnemonic seed with parties you would also give access to your bank account. **Do not** share it with an exchange, a Proof-of-Stake validator, another blockchain service, or "someone from Cosmos" on the phone – these are _not_ trusted partners.

</HighlightBox>

* Keplr saves your seed on disk but in an encrypted form.
* Keplr asks you for the **encryption password**, which is used to encrypt your mnemonic on your computer. For the password, keep in mind:
    * It should be a strong password.
    * You should save it securely too.
    * Keplr will ask you for this password every time you open the wallet and for important actions.
* If your computer or the encrypted mnemonic seed file is stolen, your wallet assets are only as well-protected as your password is strong.

![Keplr mnemonic seed and creating a password page](/keplr-mnemonic-step.png)

When you are ready, click _Next_.

You will now be challenged to reproduce your mnemonic seed phrase. If you saved your seed, you should be able to click on each word in the correct order.

![Keplr mnemonic recall prompt: selecting the correct words of your mnemonic](/keplr-mnemonic-recall-prompt.png)

When done, it should look like this:

![Keplr mnemonic recall done](/keplr-mnemonic-recall-done.png)

After clicking _Register_, you are all set:

![Keplr all set](/keplr-all-set.png)

If you click on the extension icon again, you will see that you hold zero ATOMs. Your first public address is also visible in the form `cosmos1...`.

If you click on the drop-down menu labeled _Cosmos_ at the top, you can see how many assets from other supported networks you have:

![Keplr empty assets](/keplr-empty-assets.png)

<HighlightBox type="info">

Consider your wallet's "address" as you would the address of your home: it is perfectly acceptable for other people to know your address, as it allows them to send you ATOM or other assets. _Knowing an address does **not** grant access to the assets at that address._

</HighlightBox>

You can also open the [Keplr dashboard page](https://wallet.keplr.app/#/dashboard), which interfaces with the extension. **The dashboard at this address is a web page loaded from a website and, as such, is not a trusted partner.** It will never ask you for your mnemonic or your password.

<HighlightBox type="tip">

Now would be a good time for you to save your mnemonic and password safely, before you put valuables in your wallet.

</HighlightBox>

## Purchase one ATOM

How you purchase ATOM depends on your preferences, but you need to use a trusted exchange. You can purchase any amount you wish, although it is recommended to get at least 0.3 ATOM so that all of it is not consumed in transaction fees before the end of this exercise.

For the purpose of this section, it is recommended that you buy **one ATOM**.

<HighlightBox type="info">

As you can see in the [_Get ATOM and stake._ page from Cosmos](https://cosmos.network/learn/get-atom), there is a [list of exchanges](https://messari.io/asset/cosmos/markets) that are known by Cosmos for offering ATOM tokens.

</HighlightBox>

When you are done, your account on the exchange should show that you _own_ one ATOM:

![When you have one ATOM on Kraken](/kraken-one-atom.png)

However, you do not own it as you would if the token were in your Keplr wallet. Currently, it is the exchange that owns the token and assures you that they will send it to you when asked. The exchange acts like a custodial wallet.

## Withdraw your ATOM

Your exchange has a withdrawal function that allows you to send your ATOM anywhere, including to your Keplr wallet. Now it is time to set this up.

You will need your wallet address. Since the address is very long, you should avoid typing it by hand and instead copy it to the clipboard by clicking on it in Keplr:

![View of the Keplr address zone](/keplr-address-zone.png)

Go back to your exchange:

1. Paste this address where asked.
2. Ensure that it looks identical to the original you copied.
3. Proceed with the confirmation the exchange requires from you.

![Kraken: add address](/kraken-add-address.png)

When this is set, you can ask the exchange to withdraw the ATOM properly.

<HighlightBox type="note">

Take note of the transaction fee of the exchange: this is much higher than a realistic transaction fee would have been had you done the transaction yourself from within your wallet:

![Kraken exchange parameters](/kraken-exchange-params.png)

</HighlightBox>

If all went well, you should see your new asset in Keplr after a few minutes:

![Keplr received ATOM](/keplr-with-atom.png)

Congratulations! You now own slightly less than one ATOM. Remember that **you** are really in charge of this resource now, so check again that your mnemonic and password are saved properly.

<HighlightBox type="info">

You can also look at your address using a public explorer like [mintscan.io](https://mintscan.io).

</HighlightBox>

You can see the same if you open the [wallet dashboard page](https://wallet.keplr.app/#/dashboard). On this wallet page you can see a small link that leads you to your address page:

![Keplr wallet link out to address page](/keplr-wallet-link-out.png)

There you can see the transaction that originated from the exchange's wallet:

![Mintscan crediting transaction](/mintscan-crediting-tx.png)

## Stake your ATOM

Your 0.9 ATOM is now available and waiting in your wallet. It will stay there and remain 0.9 ATOM forever unless you use it for something.

_What about participating in the security of the Cosmos Hub blockchain?_

You can do this by delegating some of your ATOM as stake to a network validator. A validator consists of one or more cooperating computers that participate in the consensus process by creating blocks. In exchange for this service, validators receive block rewards and share the rewards with their delegators, minus their commission. Your modest delegated stake could award you a modest share of a validator's rewards.

<HighlightBox type="tip">

When considering staking, keep in mind:

* Unlike a centralized exchange that holds your assets in a custodial wallet, when you delegate your ATOM **you remain in charge of your ATOM**. The validator does not have access to your assets. Think of your stake as a weighted vote of confidence.
* A non-zero risk is that the validator you chose behaves incorrectly or even maliciously, which exposes the faulty validator *and you* to **protocol penalties**.
* Also keep in mind that the amount you delegate **is locked** away. You would have to wait three weeks to again have access to your delegated stake should you decide to un-delegate your stake.

</HighlightBox>

Now find a validator and delegate your ATOM to it. Click the _Stake_ button in Keplr. You are presented with a list of validators:

![Keplr: list of validators](/keplr-validator-list.png)

Right away you can discard any validators that keep 100% of the rewards for themselves, as they work for custodial wallets they keep on behalf of their customers.

Pick a validator that you like and click _Manage_. You should see a link directing you to more information on this validator.

<HighlightBox type="tip">

You can find more information on each validator on [Mintscan's validator list for Cosmos](https://www.mintscan.io/cosmos/validators).

</HighlightBox>

Pay attention to the uptime, as a missed block would cost you penalties.

A validator can have small or large voting power. The larger the voting power, the more often the validator is tasked with issuing a block. Voting power is closely linked to the reward amount you can expect:

<Accordion :items="
    [
        {
            title: 'Validator with large voting power',
            description: 'If your chosen validator has large voting power, your rewards come frequently (for example, every minute) but with a relatively small value, as they are divided between many stakers.'
        },
        {
            title: 'Validator with small voting power',
            description: 'If your chosen validator has small voting power, your rewards come infrequently (for example, every hour) but with a relatively large value, as they are divided between fewer stakers.'
        },
        {
            title: 'How do you choose?',
            description: 'Ultimately, there is little difference between staking with a high power or low power validator. Over the long run, you should get the same amount in return either way. What matters is the size of your stake – the higher your stake, the greater your return.'
        }
    ]
"/>

If you like what you see, it is time to click _Delegate_ and add the sum you want to delegate. 

<HighlightBox type="tip">

Do not delegate *all* that you own, because you still need a fraction of ATOM to cover the transaction costs when you send the *delegate* transaction. You will also need further ATOM in the future to either undelegate or claim your rewards.

</HighlightBox>

Pick 0.8 ATOM and click _Delegate_:

![Keplr: delegate parameters](/keplr-delegate-params.png)

This delegation is an important action. It is the first action you take with your private key. Every time an application asks Keplr to do an important action, Keplr will ask you to confirm it:

![Keplr: delegate confirm window](/keplr-delegate-confirm.png)

You have different options for the transaction fee, based on how fast you want it to be processed. You do not need this delegate transaction to be confirmed quickly, so choose the low end of transaction fees. Once you click _Approve_, the transaction should not take longer than a couple of minutes to be confirmed.

When it is confirmed, your pending staking rewards will start accruing. They will not grow fast, because you delegated only 0.8 ATOM and they only accrue when your chosen validator issues a block. However, after perhaps 20 minutes you should see something similar to this:

![Keplr: accruing rewards](/keplr-accruing-rewards.png)

Your rewards are said to be *pending* because you need to claim them before they are yours. The claim transaction has its fees, so it is best to wait until your rewards exceed the transaction fees before submitting any claim transaction. With only 0.8 ATOM staked, you need to wait about 10 days to get something worth the claim transaction.

## Claim your ATOM

You did it – you waited 10 days and have been accruing rewards:

![Keplr: accruing good rewards](/keplr-accruing-good-rewards.png)

This now is enough to cover the claim transaction. Go ahead and claim it. Choose low fees to make the transaction worthwhile:

![Keplr: claim rewards](/keplr-claim-rewards.png)

You can now see that your rewards went straight to your wallet.

![Keplr: increased number of available ATOM tokens](/keplr-increased-available.png)

If you want to re-stake this amount and benefit from the compound effect, go ahead, but make sure you are not losing too much in transaction costs.

You have now completed this exercise. You are now set up to participate in the Cosmos Hub network, simultaneously contributing to its security and benefiting financially. Your stake is working for you as you continue your Cosmos journey!

## Next up

You have reached the end of this training course. The following sections provide a final resource bank](ADD LINK HERE) and the [final self-assessment test](ADD LINK HERE).
