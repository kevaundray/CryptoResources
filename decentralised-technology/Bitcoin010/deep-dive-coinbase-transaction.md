# Deep Dive : Coinbase Transaction

In the _'overview of bitcoin'_ _chapter_, we discussed the person who would like to be elected, getting a reward for doing a good job.

From this point onwards, the author will refer to this person as a **miner. **

Upon batching together a collection of transactions, the miner can then create one transaction that gifts him some amount of bitcoins. This transaction is known as the **coinbase transaction. **The amount that the miner gifts to himself, is decided upon by the Bitcoin consensus rules.

The Bitcoins that are transferred within this transaction come out of thin air, and have no previous inputs.

The miner can also be rewarded in **transaction fees.**

When sending a transaction, the sender can opt to give some amount in transaction fees.

_For example:_

If Alice wants to send 3 Bitcoins to Bob and pay 0.2 Bitcoins in transaction fees. She would supply an input with 3.2 Bitcoin's and send 3 to Bob. The remaining amount, if not sent back to her or someone else, will be collected by the miner as transaction fees.

_If transaction fees are optional, why would Alice opt to pay?_

As mentioned earlier, the miner **picks **the transactions that they would like to include. When searching for transactions to include into the batch of transactions, the transactions with higher transaction fees, take priority.

Since transactions are processed in batches and periodically, if you include no transaction fee, the miner may take a long time to pick to pick your transaction. Recollect that there is also a limit to how many transactions he can choose. It is normally customary, when sending transactions to include a transaction fee, so that your transaction can be included in a reasonable amount of time.

_How do I decide the right amount to put as a transaction fee?_

There are formulas that calculate the optimal amount to pay in transaction fees. In short, these formulas are based on how many inputs and how many outputs you have in a transaction. The more input and outputs, the higher the transaction fee. This is because the more inputs/outputs you have the bigger the size of the transaction. If your transaction is picked and it is quite large, it is occupying space that two or three transactions could have occupied, and will take longer to check whether all inputs are valid.

