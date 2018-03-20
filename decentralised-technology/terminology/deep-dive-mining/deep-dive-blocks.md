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

**Previous Block Hash**

**Merkle Root**

**Timestamp**

**Target**

**Nonce**



#### 

#### The List Of Transactions



