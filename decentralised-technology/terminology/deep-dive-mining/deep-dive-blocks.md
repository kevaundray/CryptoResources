# **Deep Dive : Blocks**

This chapter is being reviewed. Not suitable for consumption.

_What are blocks in Bitcoin?_

Recall in the '_overview of bitcoin' chapter_, we mentioned that the miner, collects transactions into batches. We referred to them as batches. In the bitcoin protocol, they are called **Blocks. **Blocks do not only contain information about transactions. A block consists of three components, the **block header, the list of transactions and a transaction counter.**

_Consensus rules concerning block size state that:_

* _A block must not be larger than 1MB._
* _The block header must not be greater than 80 bytes_
* _The transaction counter must not be greater than 9 bytes._
* _The list of transactions may vary, and so it will fill the bulk of the block._

#### Transaction counter

_This is a number which states the amount of transactions in this block._

#### Block Header

_This contains the summary of the block, or the metadata. _

* **Block Version**

As with transactions, blocks are data structures which can change over time. The block version number is used for backwards compatibility, in case a node is validating an older block and it has changed in structure or semantics from newer blocks. Using the block version number, he will be able to appropriately parse each one.

* **Previous Block Hash**

The Block hash is synonymous with the Block Id. The previous block hash is the hash of the contents of the block that came before this block. If the previous block's content changes, then the previous block hash changes. Since the previous block hash is a part of the contents of the current block, then the hash for the current block also changes. This principle **chains **the **blocks** together; if one block was changed then it would become evident and the change would ripple to all future blocks. This makes it extremely easy to verify whether your blockchain is different to another nodes.

* **Merkle Root**

_This chapter assumes that you have read the Merkle root chapter._

The leaves of the merkle root, will be the transaction IDs. The merkle root will therefore represent a hash such that if any of the transactions change, then the merkle root changes. Mentioned in the _Deep Dive : Full Node_, the merkle root is used so that lightweight nodes, can request merkle proofs from full nodes to verify that there specific transaction was included in a block. They cannot verify whether the block itself is valid, and so lightweight nodes must have a degree of trust with the full node, that they are requesting the information from.

* **Timestamp**

This is the time that the miner completed the block. The degree of variance that this number may have is two hours. The reason why a miner would want to change this value to not be indicative of the true time, will be discussed in _Deep Dive : Mining._

* **Target**

Target is an indicator of how hard the work that the miner has to complete is. In short, this is what Bitcoin uses to ensure that on average, the work takes 10 minutes. We will go into further detail on this in '_Deep Dive : Proof Of Work'_

* **Nonce - Max 32 bytes**

The nonce is a number. It is related to the target and is used by the miner, in order to complete the _work_. For all intents and purposes, since we are only concerned with the _Blocks_. This definition is sufficient. We will go into further detail on this in '_Deep Dive : Proof Of Work'_

#### The List Of Transactions

_This field lists all of the transactions in this Block, all of the transactions that the miner has picked out the mempool._

