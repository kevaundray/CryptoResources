# **Deep Dive : Blocks**

_NOTE: REWRITE DEEP DIVE: MINING WITH THE ASSUMPTION THAT THE USER HAS READ DEEP DIVE BLOCKS. WE CANNOT GET A FULL EXPLANATION OF DEEP DIVE : MINING WITHOUT DEEP DIVE: BLOCKS_

_What are blocks in Bitcoin?_

Recall in the overview of bitcoin section, we mentioned that the elected person, collects transactions into batches. We referred to them as batches, in the bitcoin protocol we will call them **Blocks. **Blocks do not only contain information about transactions. A block consists of three components, the **block header, the list of transactions and a transaction counter.**

Consensus rules concerning block size state that:

* A block must not be larger than 1MB.
* The block header must not be greater than 80 bytes
* The transaction counter must not be greater than 9 bytes.
* The list of transactions may vary, and so it will fill the bulk of the block.

#### Transaction counter

_This is a number which states the amount of transactions in this block_

#### Block Header

_This contains the summary of the block, or the metadata. _

_                
_**Block Version**

As with transactions, blocks are data structures which can change over time. The block version number is used for backwards compatibility, in case someone goes back and wants to check the blocks.

**Previous Block Hash**

The Block hash is synonymous with Block Id. The previous block hash is the hash of the contents of the block that came before this block. If the previous block changes, then the previous block hash changes. Since the previous block hash is a part of the contents of the current block, then the hash for the current block also changes. This principle **chains **the **blocks** together.

Again, If one block is changed, then all blocks after that block is also changed. This is because each block is linked to the previous block via the previous block hash, and the previous block hash is calculated by hashing the content of the block.

**Merkle Root**

_This chapter assumes that you have read the Merkle root chapter._

The leaves of the merkle root, will be the transaction IDs. The merkle root will therefore represent a hash such that if any of the transactions change, then the merkle root changes.

**Timestamp**

This is the time that the person elected included was finished completing this block and appending it to other peoples database.

**Target**

As mentioned in the\_ 'Deep Dive : mempool'  \_chapter, the work that the person is completing in the block. Will be dynamically adjusted, so that on average it takes 10 minutes to complete. This target field is an indicator of how hard the work is. We will go into further detail on this in '_Deep Dive : Proof Of Work'_

**Nonce**

The nonce is a number. It is related to the target and is used by the person who wants to be elected, in order to complete the work. For all intents and purposes, since we are only concerned with the _Blocks_. This is a sufficient enough definition.

#### The List Of Transactions

_This chapter assumes that you have read the 'Deep Dive : Transactions' chapter._

_This field lists all of the transactions in this Block. In other words, all of the transactions that the person who would like to be elected has picked out the mempool._

