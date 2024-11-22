---
description: Describes the resistance against blockchain analysis implemented in Scala
---

# Blockchain analysis resistance

There are many academic papers dedicated to the analysis of the Bitcoin’s blockchain. Their authors trace the money flow, identify the owners of coins, determine wallet balances and so on. The ability to make such analysis is due to the fact that all the transfers between addresses are transparent: every input in a transaction refers to a unique output. Moreover, users often re-use their old addresses, receiving and sending coins from them many times, which simplifies the analyst’s work. It happens unintentionally: if you have a public address (for example, for donations), you are sure to use this address in many inputs and transactions. Scala’s CryptoNote is designed to mitigate the risks associated with key re-usage and one-input-to-one-output tracing.&#x20;

Every address for a payment is a unique one-time key, derived from both the sender’s and the recipient’s data. It can appear twice with a probability of a 256-bit hash collision. As soon as you use a ring signature in your input, it entails the uncertainty: which output has just been spent? Trying to draw a graph with addresses in the vertices and transactions on the edges, one will get a tree: a graph without any cycles (because no key/address was used twice). Moreover, there are billions of possible graphs, since every ring signature produces ambiguity. Thus, you can’t be certain from which possible sender the transaction edge comes to the addressvertice. Depending on the size of the ring you will guess from “one out of two” to “one out of a thousand”. Every next transaction increases the entropy and creates additional obstacles for an analyst.



![](https://gblobscdn.gitbook.com/assets%2F-LV59Y28GtFOLyQ3_Vax%2F-LV5EKkEyBPy283f7Znv%2F-LV5H9tItvHK-8jX1XOc%2Fimage.png?alt=media\&token=445a5367-dc25-4fe8-ae14-676971461edd)
