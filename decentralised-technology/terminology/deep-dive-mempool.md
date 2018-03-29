# Deep Dive: Mempool

Following from the _overview of Bitcoin chapter_. We mentioned that the miner will

> take as many transactions as the rules says he can take, from this list of unconfirmed transactions

This list of unconfirmed transactions is known as the **memory pool**. Each full node has it's own copy of a memory pool and the size of it varies.

In the Bitcoin network, the miner is only allowed to take 1MB of transactions. These are a part of the bitcoin consensus rules.

There has been debate on allowing the miner to take more than 1MB, so more transactions can be processed in a single batch. This debate ties into the question of '\_how do we make Bitcoin scale to that of VISA or Mastercard?' \_This is however beyond the scope of this book and will not be discussed further.

~~NOTE TO SELF:~~

~~// Everything below this will be deleted, if no better use can be found of it.~~

~~// The reason is because, we have not discussed POW as of yet and so the 10 minute interval may confuse the reader,~~

~~// We are following along from the Overview of bitcoin. In the overview, we discussed the miner putting money into the middle. This money is in the form of electricity cost.~~

~~We also discussed a periodical changing of the person elected. To be more concise, the Bitcoin network makes the 'work' the person who wants to be elected, hard enough that it can only be solved in 10 minutes. The difficult increases if more people are finding this work easy.~~

~~This means that if the memory pool has 9MB of transactions, and you decide that you want to send Bitcoins. It will take on average 10 \* 9 = 90 minutes for your transaction to confirm.~~

