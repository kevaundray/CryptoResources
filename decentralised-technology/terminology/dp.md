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

We will now outline the process in which mining is done:

1. 


