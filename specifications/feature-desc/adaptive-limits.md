---
description: Describes the adaptive parameters of the Scala Blockchain
---

# Adaptive Limits

A decentralized payment system must not depend on a single person’s decisions, even if this person is a core developer. Hard constants and magic numbers in the code deter the system’s evolution and therefore should be eliminated (or at least be cut down to the minimum). Every crucial limit (like max block size or min fee amount) should be re-calculated based on the system’s previous state. Therefore, it always changes adaptively and independently, allowing the network to develop on it’s own. Scala’s CryptoNote has the following parameters which adjust automatically for each new block:



*   **Difficulty**

    The general idea of our algorithm is to sum all the work that nodes have performed during the last 720 blocks and divide it by the time they have spent to accomplish it. The measure of the work is the corresponding difficulty value for each of the blocks. The time is calculated as follows: sort all the 720 timestamps and cut-off 20% of the outliers. The range of the rest 600 values is the time which was spent for 80% of the corresponding blocks



*   **Max block size**&#x20;

    Let MN be the median value of the last N blocks sizes. Then the “hard-limit” for the size of accepting blocks is 2\*MN. It averts blockchain bloating but still allows the limit to slowly grow with the time if necessary. Transaction size does not need to be limited explicitly. It is bounded by the size of the block.
