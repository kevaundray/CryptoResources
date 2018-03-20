# Deep Dive : Coinbase Transaction

In the '_overview of bitcoin' chapter, _we discussed the person who would like to be elected, getting a reward for doing a good job.



Upon batching together a collection of transactions, the person who would like to be elected can then create one transaction that gifts him some amount of bitcoins. This transaction is known as the **coinbase transaction.**



The Bitcoins that are transferred within this transaction come out of thin air, and have no previous inputs.



The person who would like to be elected can also be rewarded in **transaction fees.**

When sending a transaction, the sender can opt to give some amount in transaction fees.

For example:

If Alice wants to send 3 BTC to Bob and pay 0.2BTC in transaction fees. She would setup an inout with 3.2 BTC and send 3 to Bob. The remaining amount, if not sent back to her or some address, is assumed to be transaction fee for the miner.

_If transaction fees are optional, why would Alice opt to pay?_

As mentioned earlier, the person who would like to be elected **picks **the transactions that they would like to include. When searching for transactions to include into the batch of transactions, the transactions with higher transaction fees, take priority.

