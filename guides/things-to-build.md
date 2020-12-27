---
title: Build Payshares Apps
---
Build cool things on Payshares! This list outlines a few ideas for applications. Feel free to add your own or take one here and run with it.
As always, if you need help building anything with Payshares, just ask on [Slack chat](http://slack.payshares.org/), [IRC](https://kiwiirc.com/client/irc.freenode.net/#payshares-dev), or email developers@payshares.org.

If you're not looking for a full-blown project but still want to help out, look for `help wanted` issue labels in any of our [repos](https://github.com/payshares).

# Slack Bot
- Report a stream of all payshares transactions to a channel.
- *Advanced*: Allow people to send money/points/+1's to other Slack team members `/send @bob $5`.

# API Mashups
- Twilio meets Payshares: SMS alerts for transactions (you can check the example [here](https://github.com/payshares/payshares-sms-client))
- Twitter meets Payshares: Tweet to send money or Twitter alerts
- Reddit meets Payshares: Tipbot!
- Many more possibilities

# Graph of Horizon data
A relatively simple project that graphically displays information pulled from Horizon and could look up accounts and transactions. It would also be cool to see:
 - Tree of account creation. All accounts are created by other accounts, so you could show this tree of lineage.
 - Graph of ledger header info over time:
   - Transaction count
   - Operation count
   - Ledger close times
   - Fee pool

# Federation Service
Implement a simple [Federation server](https://www.payshares.org/developers/guides/concepts/federation.html) and setup a webpage where anyone can claim a name*yourdomain.com payshares address and associate their payshares account ID with it. The catch is your service will only federate for accounts that set their [inflation destination](https://www.payshares.org/developers/guides/concepts/inflation.html) to one provided by your domain.

You can also contribute to the [federation server](https://github.com/payshares/go/tree/master/services/federation) maintained by Payshares Development Foundation.

# Stakks to any email address
Allow anyone to send stakks from their Payshares client to any email address. They would simply enter something like `<emailaddress>*domain.com` and then they are able to send it stakks. If the recipient doesn't have a payshares account already one will be created for them and they will get an email alerting them that they have stakks.

This would be a service hosted at `domain.com` that does the following:
- Runs a federation server.
- Will federate payment addresses with an email prefix like `jed@payshares.org*domain.com`.
- If there is a federation request for an address you don't know that starts with a valid email address:
  - Generate a key pair
  - Return the generated public key as the accountID
  - Watch the network to see if that account is created.
  - If the account is created, you send an email to the given email address with the private half of the keypair with links to a Payshares client.

*Advanced* allow people to manage the payshares account you just created for them by sending emails to control@domain.com. This makes someone's inbox a Payshares client. For example: `send 100 XPS to bob@gmail.com`

[Adding this feature to a wallet](https://galactictalk.org/d/37-project-idea-sending-stakks-to-any-address)

# Distributed Exchange
Description and discussion [here.](https://galactictalk.org/d/26-project-idea-distributed-exchange)


# Resource Paywall
Let's say you have a public-facing service, perhaps for streaming or open wifi. You want to allow other people to use this service if they pay you small amounts. These payments could be used for spam prevention or to support your business. This is a job for the **toll collector**...

## Toll Collector
A simple service that keeps track of any XPS sent to a `toll address`. The toll collector has a database of public keys and amounts of XPS it has sent to the toll address. It watches for payments to the toll address on the Payshares network and adds them to this DB.

The toll collector service has one RPC or endpoint that you can call:

  - `charge(publicKey, amount of XPS)` returns
    - `amount XPS charged`
    - `amount of XPS this key has left`

Your app can publish its Payshares toll address for payments. When someone tries to use your service, the server has them authenticate their public key and calls `charge` on the Toll Collector to decrements the consumer's balance in the DB. You can send the consumer a message when their balance is zero.

# Multisig Coordinator
A web application that facilitates creating multisig transactions. Typically you must coordinate between several parties to generate a transaction for an account protected by multisig. This site would make this process much easier and allow you to coordinate in cases where you don't know the other party.

Ideally, the multisig coordinator includes the following features:
- Associate an email address with your public key
- Create a tx that you would like to be signed by multiple parties
- Enter the public keys that you would like to sign the tx
- If any of these keys have previously associated their email address, then they will be sent a message
- When you come to the site you see a list of all pending transactions:
  - You can see the details of each transaction
  - You can see who initiated the transaction
  - You can see who else has signed the transaction
  - You can sign any that are waiting for you
- Once a pending transaction is signed by enough people, it is submitted to the network
- Once the transaction is submitted, all the signers are notified

# Market Feed
Data feed for the distributed Exchange inside Payshares. Something equivalent to the [Poloniex API](https://poloniex.com/public?command=returnTicker).
This will be useful for apps like [paysharesTerm](http://paysharesterm.com) as well as getting the Payshares trade volume added to charting sites like [CoinMarketCap](http://coinmarketcap.com)

# Quorum Monitor
A web page that shows the state of the network quorum graph. Ideally, the quorum monitor shows:
- A live graph of how the network is connected
- What servers are having issues
- Any servers that disagree with the rest of the network
- Perhaps a history of uptime for each validator

You should be able to view the quorum graph from the point of view of any given validator. You would probably need to run payshares-core to build the quorum monitor. You can get the data from the payshares-core logs and the /quorum command.

*Advanced*: Build a server that connects to payshares-core and monitors the externalized messages and the various validator broadcasts.

# Libraries
Build a library in your favorite language:
- C#
- PHP
- Haskell
- Other languages

Or contribute to our existing SDKs:
- [JavaScript](https://github.com/payshares/js-payshares-sdk)
- [Go](https://github.com/payshares/go)
- [Java](https://github.com/payshares/java-payshares-sdk)
- [Python](https://github.com/PaysharesCN/py-payshares-base/)

# Product and Service Ideas We've Heard
- Microsavings account for school, health, insurance
- Microinsurance
- P2P lending
- Conditional cash transfers
- Donation systems for nonprofits
- Loyalty points programs
- Community currencies
- Time banks
- Volunteer hour tracking
- Anywhere ATM or human ATM mobile apps

# Atomic cross-chain swap facilitator
- End-user software that to facilitate atomic cross-chain swaps with
  various other cryptocurrencies (between both Stakks and other
  Payshares currencies).
- A rendezvous service establishing a marketplace for cross-chain
  swaps.
