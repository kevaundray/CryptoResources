# Deep Dive: Mempool

Following from the overview of Bitcoin. We mentioned that the person who would like to be elected, will

> take as many transactions as the rules says you can take, from this list of unconfirmed transactions

This list of unconfirmed transactions is known as the **memory pool**. Each full node has it's own copy of a memory pool and the size of it varies.

In the Bitcoin network, the person who would like to be elected is only allowed to take 1MB of transactions. These are a part of the bitcoin consensus rules, that were discussed earlier.

We also discussed a periodical changing of the person elected. To be more concise, the Bitcoin network makes the 'work' the person who wants to be elected, hard enough that it can only be solved in 10 minutes. The difficult increases if more people are finding this work easy.  
  
This means that if the memory pool has 9MB of transactions, and you decide that you want to send Bitcoins. It will take on average 10 \* 9 = 90 minutes for your transaction to confirm.

