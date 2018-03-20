# Deep Dive: ScriptSig and ScriptPubKey

Following the '\_Deep dive: Transactions' \_chapter, we will go into more detail on two fields; scriptSig and scriptPubKey.

This chapter assumes that you have read the Blockchain Foundation module, and or you have a solid understanding of hashing and encryption.

#### 

#### Script Public Key \(ScriptPubKey\) - Locking Script

In the previous chapter, we alluded to the fact that the scriptPubKey specifies who the amount of bitcoins is being sent to. The scriptPubKey however, does not specify an Address like with a bank you would specify the receivers account number. Instead, it specifies a script that must evaluate to true.

_Why provide a script and not the to address?_

To understand this, we need to think about how we would specify in the transaction, that you would like to send 0.5 bitcoins to a shared address that can only be spent, if two out of the three people sharing it, agree. In short, this is not possible. Using a script allows you to add the above features and more.

```
OP_DUP OP_HASH160 01c801d8687ab1c05c23bb8cd8110203072a29e6 OP_EQUALVERIFY OP_CHECKSIG
```

The above is an example of an "output" address. You are not expected to understand the semantics.  
The script above states that given a **public key **and **a digital signature**.

If:

* After hashing the public key given, and applying some other operations. It matches the output I state.

AND

* The digital signature provided matches the public key and states that they would like to spend these funds on the given output.

_Return True_

Let's break that down a little further:

##### Condition 1:

Given the public key, If I can hash it and perform some amount of manipulation to it and it evaluates to the **public address. **

Then this condition is true.

Note: The public key is not the public address. The **public address**, which normally begins with a 1 in Bitcoin, is derived from the **public key. **

**Condition 2:**

Given the digital signature. If it matches the public key provided and it states that the user would like to spend that particular input.  
Then this condition is true.

#### Script Signature \(ScriptSig\) - Unlocking Script

In the previous chapter, we alluded to the fact that the script signature was used so that one can prove that they are who they say they are, that they do own the inputs that they are attempting to spend.

The scriptsig is used to unlock the scriptPubKey or make the funds locked by the scriptPubKey available, by providing two components. A **public key **and a **digital signature.**

The digital signature is a signed hash of the transaction that the sender is trying to unlock.

If this still alludes you, then a simple analogy would be as follows.

Alice sends 5 BTC to Bob.  
She creates a transaction and proves that she can spend 5 BTC , using her ScriptSig in the input.  
She then states in the output that the 5 BTC can be spent, by whomever can unlock the script.  
Bob can only unlock this script, if the public key provided can be turned into Bob's public address and if the digital signature provided matches the public key and approves the funds to be spent.t

