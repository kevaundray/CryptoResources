# Deep Dive : Mining

This chapter is being reviewed. Not suitable for consumption.

The reason we introduced miners was to stop 'double spend' attacks. This is where a bad actor tries to spend the same funds twice.

Formalising, what we have learnt so far:

* Miners choose transactions from the **mempool **, they are batched into **blocks**
* The miner then verifies each transaction is valid. For a miner to do this, he must also be a full node, as he needs to have the UTXO list to verify whether an input has been spent already.
* The miner then iterates through the **nonce **value in the _block header_, hashing the _block_ each time until the output is below the desired _target_. This process is known as **Proof of work.**
* Once the desired hash output is acquired , the miner broadcasts to the rest of the network and the _full nodes_ verify that the work he has done is _correct_.
* If the majority of full nodes validate the block using the consensus rules and deem it a valid block, then the miner is rewarded with the coinbase transaction.
  _The coinbase transaction is included in the block that the miner has mined and if the block is valid, so is his transaction._
* If the majority of full nodes verify, the block and it is deemed as invalid, i.e. it does not comply with the consensus rules. Then the block will be rejected, and the miner will be kicked from the network for supplying an invalid block for a certain period of time, depending on what the violation of the rules were. The miner would be at an economic loss due to doing the proof of work.

**The miners must follow the Bitcoin consensus rules which are enforced by the full nodes. **

_Where can you find the list of consensus rules?_

In the code. To my knowledge there is no website that has gathered the explicit rules in terms of mining blocks and so in order to find them , you will need to inspect the code and or ask another miner who has enough experience.

We will now outline the process in which mining is done in regards to the whole Bitcoin network:

1. Alice creates a transaction. The transaction states that only the person with a specific **public key hash **, may spend these funds. The person in ownership of the public key and can also provide a signature with the corresponding private key, is Bob. 
2. She then broadcasts this transaction to the full nodes in the network.
3. Each person on the network, who is a full node, collects these transactions into their **mempool.**
4. If a miner is also a full node, then the miner verifies the transaction and starts to build a block with Alice's transaction and many other transactions.
5. The miner then starts to mine the block looking for a nonce value in the block header which when hashed, equates to less than the target number; Proof Of Work. 
6. Once this nonce and hash been found. The miner then broadcasts this block to the rest of the network. If no other miner has broadcasted a block with those transactions and the block is valid. Then he will rewarded with the coinbase transaction.

_Possible questions:_

_Why do full nodes have mempools if they are not going to mine?_

One reason a full node who is not a miner, may keep a mempool is so that they re-broadcast the transactions in their mempool. In hopes that it will reach a miner faster.

_What if two miners validate a block at the same time?_

This will be covered in 'Forks' and other chapters

_What happens if a miner is not a full node?  
_If a miner is not a full node, this means that he does not have the UTXO set, discussed in 'Deep Dive : Full Nodes' and so he is not able to verify the transactions he is given. If he receives an invalid transaction, one that someone is trying to spend twice, then when he solves the block, the network will reject his block and he will have wasted electricity on the proof of work.

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

If the price of a lottery ticket were to reduce to $0.00002 then everyone would buy one. The financial burden of losing $0.00002 is negligible, and so if you do not get it on this ticket, you do not care. If the ticket gets wet you may not care also, if you lose 10 tickets you may not care.

If a ticket were to cost $100 however , you would take extra precaution when buying it, you would make sure that it was in the right conditions to submit incase you won, i.e. not wet or ripped and not winning would weigh heavier on you.

**The great electricity expenditure is not a flaw in the system, it was made that way by design. Whether the economical loss of proof of work outweighs what Bitcoin could be, is another discussion.**

