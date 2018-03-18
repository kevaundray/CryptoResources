# **Deep Dive : Mining**

The elected person we alluded to earlier, is known in the Bitcoin protocol as a **miner**.

As mentioned before, the reason we have miners is to stop 'double spend' attacks, whereby a bad actor tries to spend the same funds twice.

We also alluded to the miners choosing batches of transactions and verifying them. In the Bitcoin protocol, the batches are known as **Blocks. ** They contain more than just the transactional information. We will get to this when we get to the "Deep Dive: Blocks" chapter.

The miners must follow the Bitcoin consensus rules, which have a section that tells them how to verify transactions and how to submit a valid block.

_Where can you find the list of consensus rules? _

In the code. To my knowledge there is no website that has gathered the explicit rules in terms of mining blocks and so in order to find them out, you will need to inspect the code and or ask another miner who has checked the code.

We will now outline the process in which mining is done:

1. Alice sends Bob 5BTC.
2. Alice Broadcasts this transaction to the whole network
3. Martin, A miner hears news of this transaction.
4. Martin verifies that this transaction is valid.
5. He then verifies this transaction and adds it into memory to hold for about 10 minutes.
6. After 10 minutes, Martin gets all of the transactions that he verified from memory and puts them into a Block, along with another field called a _nonce. Note: There are more fields, this is a deep dive : mining and so we are not too worried about the details in the block that does not pertain to mining._
7. He then starts to hash the Block, incrementing the field called the nonce from zero to 4 billion.
8. Once he finds a hash output with a certain pattern, in Bitcoin, it is a pre-requesite of zeroes. Then he can submit the block and receive his reward. _Remember: There are other miners in the network who are trying to 'mine a block' and so the fastest one will win. The fastest one is the one elected to append to the block._

_What is a nonce and why do miners use it?_

It is a random number that can only be used once. A miner uses it because he needs a pre-requesite amount of zeroes from the hash, and so incrementing the nonce changes the output. He can increment to 4 billion looking for a hash with for example four leading zeroes.

_What happens if the miner gets to four billion and he does not get the amount of leading zeroes?_

That is a good question, and we will go 



