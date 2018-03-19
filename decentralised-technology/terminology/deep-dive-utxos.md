# Deep Dive: UTXOs

Imagine a world in which there were no pennies and notes were exact chnage.

For example, you go to the supermarket and you want to buy a drink for $1. You have a $20 note. You give the cashier the $20 note and for your _change _ she gives you back a $19 note. You now have an unspent $19 note.

Another example, you go to the electronic store and you buy groceries. The groceries cost $24.90. You have a $35.85 note, which you give to the cashier. She gives you back as _change a_ $10.95 note. You now have an unspent $10.95 note.

A harder example. Let's say you go to the store to buy a game for $35. You have a $20 note, a $10 and a $6 note. Your unspent notes all sum to $36. You give this to the cashier, and she gives you back a $1 note. You now have an unspent $1 note.

This is an important concept that Bitcoin uses. The important thing to note, is that no matter what your change is, you will always get a note back. The notes, just like money in the real world, are indivisible, you cannot rip a $20 note in half and have half the value, for example.

In Bitcoin transactions work in a similar manner. Relating back to the \_overview of Bitcoin, \_If Alice wants to send 5 Bitcoins to Bob, and in the past she has received 3 Bitcoins from Sally and 3 Bitcoin from James. Then  in order to send Bob 5 Bitcoins, she must send the 3 Bitcoin that she received from Sally and the 3 Bitcoins that she received from James. This means that she is sending a total of 6 Bitcoins. She only wants to send 5 to Bob, so what she will do in the Bitcoin software, is she will send the remaining Bitcoin to herself.

If that sounded confusing, then imagine that the cashier in the shop is the Bitcoin software and we are in the weird world we described above. Alice gives the cashier 6 Bitcoins with a note, because she only has two 3 Bitcoin notes, one she received from Sally and one She received from James. The note states that she wants to send 5 Bitcoins to Bob and she wants the change to go back to her. The cashier gives 5 Bitcoins to Bob, and gives Alice a 1 Bitcoin 'note'.

_We will discuss what happens when Alice decides to not state that she would like the change to go back to her, in a later chapter_

In order to test your understanding, we will go over some questions:

> 1\) _Alice has now received 1 Bitcoin, from her transaction with Bob. She would like to now send Kate, 0.5BTC for a new phone and Nicole 0.2BTC for a new computer. Describe the process for this transaction._

Formalising this a bit, A transaction has inputs and outputs. Alice uses some amount of Bitcoins as **input **and Bob gets some amount of Bitcoins as **output.**

Let's do another example with this terminology.

Alice has 6 Bitcoins that she received from James. She wants to send_ 5BTC_ to Bob. She forms a transaction by supplying her **6 BTC as one input to this transaction. **She then states that this transaction will have two **outputs. **One will send 5BTC to Bob. The other will send 1BTC back to Alice.

Formalising this further, the two outputs from the transaction above are unspent. They are called **Unspent Transaction Outputs \(UTXOs\).**

If Alice decides to use her 1BTC or Bob decides to use his 5BTC, then the transaction output will no longer be unspent. It will then be called a **Spent Transaction Output.**

> True or False: Only UTXOs can be used as inputs to transactions

We will now call **inputs** to a transaction, **Unspent Transaction Outputs**. This is because you can only spend Bitcoin which you have, and if you have Bitcoin then someone must have given it to you from a previous transaction. Therefore, all inputs will be **unspent** and would have came from previous **transaction outputs.**

In order to finalise this chapter, we will need to dive one level deeper.

Bitcoin has no concept of what an account is. All it sees, is previous unspent transaction outputs becoming spent transaction outputs. Essentially, the Bitcoins are changing ownership. When Alice send 5BTC to Bob, she is telling Bitcoin that Bob is the only person who can unlock these Bitcoins.

_Possible questions you may have:_

_Why does Bitcoin not work like a normal account, where you can send any amount_

_I thought that Bitcoin was anonymous, how can Alice know Bob?_

Bitcoin is pseudo-anonymous. The names Alice and Bob are an oversimplification of how identities actually work in Bitcoin. This chapter was solely used as a means to understand the UTXO model.

