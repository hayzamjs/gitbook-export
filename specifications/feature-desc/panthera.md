---
description: Describes the proof-of-work (PoW) algorithm used in the blockchain.
---

# Panthera PoW algorithm

## (RandomX + Yespower + KangarooTwelve) = Panthera <a href="#ddf6" id="ddf6"></a>

![](<../../.gitbook/assets/panthera (1).png>)

Scala uses an algorithm technology combining [RandomX](https://github.com/tevador/RandomX) with our own variant of [yespower](https://www.openwall.com/yespower/)_._ In addition we have combined a quantum resistant algorithm called [KangarooTwelve](https://keccak.team/kangarootwelve.html) to create a new PoW algorithm that we called _Panthera_.&#x20;

It is faster than RandomX and is extremely resistant to not just _ASICs_ and _FPGAs,_ but is also rated level 2 quantum-resistant due to the inclusion of K12.

## Technical details <a href="#id-9337" id="id-9337"></a>

_RandomX_ utilizes a virtual machine that executes programs in a special instruction set that consists of integer math, floating point math and branches.

These programs can be translated into the CPU’s native machine code on the fly. At the end, the outputs of the executed programs are consolidated into a 256-bit result, using a cryptographic hashing function (_Blake2b_).

In **Panthera**, the [Blake2b](https://en.wikipedia.org/wiki/BLAKE_\(hash_function\)) hash is further hashed using Yescrypt-RH and KangarooTwelve, which makes it much more difficult for GPUs to attain an unfair advantage, and which also allows the algorithm to be resistant to ASICs/FPGAs and level 2 quantum computers.

