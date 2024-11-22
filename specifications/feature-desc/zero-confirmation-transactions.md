---
description: Description of Zero Confirmation transaction on the scala blockchain.
---

# Zero confirmation transactions

One of Scala's main goals are to get adopted by the masses, to be used in everyday life for simple transactions. This is greatly hindered by the fact that transactions takes time to be added into blocks. We have made a custom point-of-sale system that works with our mobile wallets to allow transactions to go through to a merchant in less than a few seconds.

The inner working of this function are very simple. When a transaction is broadcast onto the network, it first goes into a pool of transactions called the transaction pool or the memory pool, from here it is added onto a block, even with our block time being 120 seconds, it could take a couple of minutes more depending on amount of transactions in the pool. To avoid this waiting period we are allowing merchants to accept 0 confirmation transactions. The point of sale will also come with an option where the merchant can set the amount of confirmation needed, for instance if the transaction is of high value.

Another solution we provide to the users is to use a semi-custodial application called ScalaPay which uses a centralized database of transaction to be handled in a similar fashion of how traditional exchanges handle them, which is by using a simple pool of transactions on a single server before doing a commit onto the network, this is mostly for the novice users for whom setting up a regular node or a node which connects to a remote node is not feasible. Thus increasing even more the adoption capabilities.
