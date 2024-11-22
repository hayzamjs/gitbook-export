---
description: Describes how Scala defends itself against double-spending.
---

# Double-spending proof

Fully anonymous signatures would allow spending the same funds many times which, of course, is incompatible with any payment system’s principles. The problem can be fixed as follows.

A ring signature is actually a class of crypto-algorithms with different features. The one Scala’s CryptoNote uses is the modified version of the “Traceable ring signature”. In fact we transformed traceability into linkability. This property restricts a signer’s anonymity as follows: if he creates more than one ring signature using the same private key (the set of foreign public keys is irrelevant), these signatures will be linked together which indicates a double-spending attempt.

To support linkability, Scala's CryptoNote introduced a special marker being created by a user while signing, which we called a key image. It is the value of a cryptographic one-way function of the secret key, so in math terms it is actually an image of this key. One-wayness means that given only the key image it is impossible to recover the private key. On the other hand, it is computationally impossible to find a collision (two different private keys, which have the same image). Using any formula, except for the specified one, will result in an unverifiable signature. All things considered, the key image is unavoidable, unambiguous and yet an anonymous marker of the private key.

![](https://gblobscdn.gitbook.com/assets%2F-LV59Y28GtFOLyQ3_Vax%2F-LV5EKkEyBPy283f7Znv%2F-LV5H-FsVKTRxBB49SDk%2Fimage.png?alt=media\&token=d5e390d8-0605-4342-8070-ab8880563c90)

All users keep the list of the used key images (compared with the history of all valid transactions it requires an insignificant amount of storage) and immediately reject any new ring signature with a duplicate key image. It will not identify the misbehaving user, but it does prevent any double-spending attempts, caused by malicious intentions or software errors.



![](https://gblobscdn.gitbook.com/assets%2F-LV59Y28GtFOLyQ3_Vax%2F-M-SPK6pc0oPyHg8JwD6%2F-M-SQGTFUxa0zXpnocFa%2FScala%20Wiki%20Double%20Spending%20Proof%20Remake.png?alt=media\&token=a51c453f-384f-4ae5-8ce2-10692a5999a0)

