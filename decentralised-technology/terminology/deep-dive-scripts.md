# Deep Dive: ScriptSig and ScriptPubKey

Following the '\_Deep dive: Transactions' \_chapter, we will go into more detail on two fields; scriptSig and scriptPubKey.

This chapter assumes that you have read the Blockchain Foundation module, and or you have a solid understanding of hashing and encryption.

#### 

#### Script Public Key \(ScriptPubKey\)

In the previous chapter, we alluded to the fact that the scriptPubKey specifies who the amount of bitcoins is being sent to. The scriptPubKey however, does not specify an Address like with a bank you would specify the receivers account number. Instead, it specifies a script that must evaluate to true. The programming language used in the script pubKey will be tackled in a later chapter and so for now, we will convert it to pseduo 

#### Script Signature \(ScriptSig\)

In the previous chapter, we alluded to the fact that the script signature was used so that one can prove that they are who they say they are, that they do own the inputs that they are attempting to spend.

This is achieved using

