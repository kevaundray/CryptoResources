# Deep Dive : Mining

The elected person we have continually eluded to, is known in the Bitcoin protocol as a **miner**.

As mentioned before, the reason we have miners is to stop 'double spend' attacks, whereby a bad actor tries to spend the same funds twice.

Formalising, what we have learnt so far:

* Miners choose transactions from the **mempool**, they are batched into **blocks**
* The miner then iterates through the **nonce** value in the **block header, **hashing the block each time until the output is below the desired **target. **This process is known as **Proof of work**.
* Once this target has been reached, the miner tells the rest of the network and the **full nodes **verify that the work he has done is correct.
* If the majority of full nodes verify the block using the consensus rules and deem it a valid block. Then the miner get's a reward, known as the **coinbase transaction. **_The coinbase transaction is included in the block that the miner has mined and if the block is valid, so is his transaction._
* If the majority of full nodes verify, the block and it is deemed as invalid, i.e. it does not comply with the consensus rules. Then the block will be rejected, and the miner will be kicked from the network for supplying an invalid block for a certain period of time, depending on what the violation of the rules were.

The miners must follow the Bitcoin consensus rules, which have a section that tells them how to verify transactions and how to submit a valid block.

_Where can you find the list of consensus rules? _

In the code. To my knowledge there is no website that has gathered the explicit rules in terms of mining blocks and so in order to find them , you will need to inspect the code and or ask another miner who has experience.

We will now outline the process in which mining is done in regards to the whole Bitcoin network:

1. Alice creates a transaction. The transaction states that only the person with a specific public address, may spend these funds. This person is Bob.
2. She then broadcasts this transaction to the rest of the network.
3. Each person on the network, who is a full node, collects these transactions into their **mempool.**
4. If a miner is also a full node, then the miner verifies the transaction and starts to build a block with Alices transaction and many other transactions.
5. The miner then starts to **mine the block ** looking for a hash of the block header which equates to less than the target number, by incrementing the nonce value. 
6. Once this hash hash been found. The miner then broadcasts this block to the rest of the network. If no other miner has broadcasted a block with those transactions and the block is valid. Then he will rewarded with the coinbase transaction.

_Possible questions:_

_What if two miners validate a block at the same time?_

This will be covered in 'Forks' and other chapters

What happens if a miner is not a full node?  
If a miner is not a full node, this means that he does not have the UTXO set, discussed in 'Deep Dive : Full Nodes' and so he is not able to verify the transactions he is given. If he receives an invalid transaction, one that someone is trying to spend twice, then when he solves the block, the network will reject his block and he will have wasted electricity on the proof of work.

_Can anyone become a miner?_

Yes, anyone can become a miner. The current target is however so low, that miners need special hardware in order to 'become elected' or find the solve the block first. Even though anyone can become a miner, only a select few will solve the block fast enough, due to better hashing hardware.

_Why do some refer to mining as a lottery?_

There is a probability of you buying a ticket and winning the lottery.

There is a probability of you finding the correct hash below the target number.

The more tickets you buy, the higher your chances

The more faster you can hash and iterate through the nonce, the higher your chance of finding the correct output.

_Some people say that Proof of Work wastes electricity, why don't we increase the target and make it easier to find blocks. This way less electricity will have been expended?_

If we increased the target number to such a number, where the blocks were no longer difficult.

1. People would start solving blocks in less than 10 minutes.
2. The punishment for getting it wrong would be reduced. When the target number is low enough, the cost of electricity to be in with a chance to solve the block first is in the tens of thousands. This is a hefty punishment to pay, if you do not stick to the rules. If we lowered the target enough, that the cost of electricity was $500, then the miner would have less of an incentive to get it right, as now it would be more lucrative to try and hack the system.

Using the lottery analogy:

If the price of a lottery ticket were to reduce to $0.00002 then everyone would buy one. The financial burden of losing  



