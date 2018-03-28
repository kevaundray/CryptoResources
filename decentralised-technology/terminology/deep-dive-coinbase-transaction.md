# Deep Dive : Coinbase Transaction

In the _'overview of bitcoin' chapte_r, we discussed the person who would like to be elected, getting a reward for doing a good job.

From this point onwards, the book will refer to this person as a **miner. **

Upon batching together a collection of transactions, the person who would like to be elected can then create one transaction that gifts him some amount of bitcoins. This transaction is known as the **coinbase transaction.**

The Bitcoins that are transferred within this transaction come out of thin air, and have no previous inputs.

The person who would like to be elected can also be rewarded in **transaction fees.**

When sending a transaction, the sender can opt to give some amount in transaction fees.

For example:

If Alice wants to send 3 BTC to Bob and pay 0.2BTC in transaction fees. She would setup an inout with 3.2 BTC and send 3 to Bob. The remaining amount, if not sent back to her or some address, is assumed to be transaction fee for the miner.

_If transaction fees are optional, why would Alice opt to pay?_

As mentioned earlier, the person who would like to be elected **picks **the transactions that they would like to include. When searching for transactions to include into the batch of transactions, the transactions with higher transaction fees, take priority.

Since transactions are processed in batches and periodically, if you include no transaction fee, the person who would like to be elected may never choose your transaction each time. Remember there is also a limit to how many transactions he can choose. It is normally customary, when sending transactions to include a transaction fee.

_How do I decide the right amount to put as a transaction fee?_

There are formulas that calculate the optimal transaction fee value. In short, these formulas are based on how many input and how many outputs you have in a transaction, the more input and outputs, the higher the transaction fee. This is because the more inputs/outputs you have the bigger the size of the transaction. If your transaction is picked and it is quite large, it is occupying space that two or three transactions could have occupied.

