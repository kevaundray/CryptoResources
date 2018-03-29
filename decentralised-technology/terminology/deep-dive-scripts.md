# Deep Dive: ScriptSig and ScriptPubKey

This chapter is being reviewed. Not suitable for consumption.

Following the _'Deep dive: Transactions' chapter_, we will go into more detail on scriptSig and scriptPubKey.

This chapter assumes that you have read the Blockchain Foundation module, and or you have a solid understanding of hashing and encryption.

#### Script Public Key \(ScriptPubKey\) - Locking Script

In the previous chapter, we alluded to the fact that the scriptPubKey specifies who the amount of bitcoins is being sent to. The scriptPubKey however, does not specify a recipient. For example, a bank would allow you to specify the account number and sort code. Instead, it **specifies a script that must evaluate to true**.

Using a script allows the Bitcoin network to be extensible and flexible in terms of what you can build on top of it. One example of this, is specifying that you only want the recipient to be able to spend the amount you send, if and only if two of the three people sharing the account agree so.

```
OP_DUP OP_HASH160 01c801d8687ab1c05c23bb8cd8110203072a29e6 OP_EQUALVERIFY OP_CHECKSIG
```

The above is an example of an "output" script. You are not expected to understand the semantics of the above script, If you are interested then a video will be linked at the bottom of this chapter.  
The script above states that given a **public key **and **a digital signature**.

If:

* After **hashing the public key** given, it **matches** with the **public key hash** that I have stated in the script: 01c801d8687ab1c05c23bb8cd8110203072a29e6.

AND

* The **digital signature** provided **matches the public key** and states that they would like to spend these funds on the **given output.**

_Return True_

* In order to send funds to Bob, you must first collect his public address. 
* From the \_Deep Dive : Identity \_section, note that the public address is a concatenation of the version byte, the public key hash and a checksum. 
* Extracting the public key hash from the public address, you will then create a script that states that these funds are 'locked' and can only be spent if the public key that hashes to this public key hash is given, and a valid digital signature stating that you would like to spend these funds are given.
* The digital signature will be verified using the public key given.

#### Script Signature \(ScriptSig\) - Unlocking Script

In the _'Deep Dive : Transactions' chapter _, we alluded to the fact that the script signature was used so that one can prove that they are who they say they are, that they do own the inputs that they are attempting to spend.

The scriptsig is used to unlock the scriptPubKey or make the funds locked by the scriptPubKey available, by providing two components. A **public key **and a **digital signature.**

The digital signature is a signed hash of the **current transaction** that he is trying to initiate with the scriptSig field, left blank.

The current transaction will inherently contain the locking script for those he would like to send funds to, and the locked script that this digital signature can unlock.

From the _Deep Dive : Transactions chapter, _note that each input contained a scriptSig section as each input needed to be unlocked separately.

For more information on scriptSig and ScriptPubKey, the author highly recommends watching tutorials 5 to 6.7, as the videos go into further detail on this subject.

https://www.youtube.com/playlist?list=PLt4veyhkEsrjzjP\_Seeu-UbjSnF6xIzgF

