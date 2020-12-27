---
title: Payshares Network Overview
---
![Payshares Ecosystem](https://www.payshares.org/wp-content/uploads/2016/06/Payshares-Ecosystem-v031.png)

Using the Payshares network, you can build mobile wallets, banking tools, smart devices that pay for themselves, and just about anything else you can dream up involving payments! Even though Payshares is a complex distributed system, working with it doesn’t need to be complicated.

## API: Horizon

**Most applications interact with the Payshares network through [Horizon](https://www.payshares.org/developers/horizon/reference/),** a RESTful HTTP API server. Horizon gives you a straightforward way to submit transactions, check accounts, and subscribe to events. Because it’s just HTTP, you can communicate with Horizon using your web browser, simple command line tools like cURL, or the Payshares SDK for your favorite programming language.

The easiest way to install Horizon is by using [**payshares/quickstart** docker image](https://hub.docker.com/r/payshares/quickstart/).

Payshares.org maintains [JavaScript](https://github.com/payshares/js-payshares-sdk), [Java](https://github.com/payshares/java-payshares-sdk), and [Go](https://github.com/payshares/go/tree/master/clients/horizon)-based SDKs for communicating with Horizon. There are also community-maintained SDKs for [Ruby](https://github.com/payshares/ruby-payshares-sdk), [Python](https://github.com/PaysharesCN/py-payshares-base), and [C#](https://github.com/QuantozTechnology/csharp-payshares-base).

## Network Backbone: Payshares Core

Behind the scenes, every Horizon server connects to **[Payshares Core](../../payshares-core/learn/admin.html), the backbone of the Payshares network.** The Payshares Core software does the hard work of validating and agreeing with other instances of Core on the status of every transaction through the [Payshares Consensus Protocol](../concepts/scp.html) (SCP). The Payshares network itself is a collection of connected Payshares Cores run by various individuals and entities around the world. Some instances have a Horizon server you can communicate with, while others exist only to add reliability to the overall network.

The easiest way to install Payshares Core is by using [**payshares/quickstart** docker image](https://hub.docker.com/r/payshares/quickstart/).

You might want to host your own instance of Payshares Core in order to submit transactions without depending on a third party, have more control over who to trust, or simply to help make the Payshares network more reliable and robust for others.

## Big Picture: The Payshares Network

The Payshares network is a worldwide collection of Payshares Cores, each maintained by different people and organizations. The distributed nature of the network makes it reliable and safe.

All these Payshares Cores—the network of nodes—eventually agree on sets of transactions. Each transaction on the network costs a small fee: 100 stroops (0.00001 <abbr title="Stakks">XPS</abbr>). This fee helps prevent bad actors from spamming the network. 

To help you test your tools and applications, Payshares.org operates a small test network and Horizon instance. [Get started with the testnet.](../concepts/test-net.md)
 
<div class="sequence-navigation">
  <a class="button button--next" href="create-account.html">Next: Create an Account</a>
</div>
