---
description: Description of our semi-decentralized checkpointing mechanism
---

# Diardi

Diardi is loosely based on the technology of dPoW created by Komodo (KMD), but the code is completely rewritten by the Scala Team.

Essentially with dPoW, you checkpoint the daemons blocks onto another stronger chain (like Bitcoin). However, we didn’t want to “bloat” Bitcoin because we all in the team love Bitcoin and thought that dPoW was just too pollutive towards other networks. We then agreed that the idea of locking a lock with another lock is not the smartest idea, because if one lock becomes weaker than the other, it can create new vulnerabilities.

Deriving from the ideas of dPoW we figured we could probably adapt it to our needs, This was the starting point of Diardi v1. So we got to work on our own version of dPoW which doesn’t use any other blockchain. Instead, our version used a blockchain that was distributed among prominent members of the community that stored checkpoints&#x20;



## **Diardi v1** <a href="#id-9337" id="id-9337"></a>

Every hard fork from the beginning the community will democratically elect 16 members from the community to run and maintain these nodes. Node operators are not required to own a single coin of Scala to run these nodes but should have expertise in the management of servers, and also a basic knowledge of blockchain technology.

In addition, because these nodes are able to be publically monitored, if they try to “cheat” in any way, their action is open to public acknowledgment, essentially undermining the validity of their own well being. And for the services provided by the maintainers of these light dPoW nodes, they will receive 90 blocks worth of rewards daily.



## **Diardi v2** <a href="#id-9337" id="id-9337"></a>

Diardiv1 was mainly something that was not tied with consensus, maintenance and checking was difficult for nodes and it was something that was ephemeral, we wanted to change that with v2.

Diardiv2 is based on a system that incorporates a completely different proof-of-work along side our main PoW Panthera.&#x20;

Each Diardiv2 node maintainer will have a specific wallet with it's very own spend and view key with which they can mine every 4th block in the network. No same wallet owner can mine 2 consecutive Diardi blocks, they're also rewarded 1/4th of the block reward for providing their service.&#x20;

## Proof-of-work and Difficulty of Diardiv2 Blocks

Felidae is the proof-of-work that the diardi maintainers will use for mining their blocks. It's orders of magnitude faster than Panthera and it was designed to be that way. Like Panthera it is also CPU friendly and is also quantum computing resistant.

Felidae uses KangarooTwelve(SHA-3) and Blake3 in tandem to generate a unique hash, Blake3 is touted as the fastest algorithm to date and K12 is rated to be level 2 quantum resistant.

The difficulty algorithm that we use for both diardi and regular blocks are the same, since Felidae algorithm is orders of magnitude faster, it will adjust as required.



## Diardiv2 Election

Diardiv1 as our community was much smaller we were able to pick out prominent members and give them the ability to checkpoint blocks, this was not democratized as we initially intended and we wanted a better way to do things from the get go.

For v2 we're doing things very differently. We believe that the major stakeholders of the project should have the most say in how the chain is being secured. Hence anyone who holds XLA will be able to redeem vXLA (vote XLA tokens) which are 1:1 in parity with XLA on a forked chain will be able to use those tokens to stake for themselves or pool tokens with other users and stake that way.&#x20;

The accounts with the most coins staked during a given period will be given the opportunity to mine Diardi blocks. Anyone holding XLA can be a part of this process. The team decides how many operators get to be on the list for instance the minimum number of people elected would be 32 and the maximum would be 128. Everything depends on the number of people that participates.









