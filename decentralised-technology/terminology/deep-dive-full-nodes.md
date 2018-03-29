# Deep Dive: Full, Pruned and Lightweight Nodes

Recalling the _'overview of bitcoin' chapter_, we mentioned that once the miner has finished his _work_, and broadcasts his batches of transactions. The others then check that it is correct, and if the majority say it is good, then he will be rewarded with the _coinbase transaction_.

The 'others' which we were referring to, are known as **Fully Validating Nodes. **The job of a fully validating node is similar to that of a judge. They receive transactions and verify them based on their own copy of the confirmed list. _Their own confirmed list_. Their own **Blockchain**. If the full node receives a block from a miner, and it is invalid, then the node rejects that block and it puts the miner who gave it the invalid block on a blacklist for a certain period of time, depending upon the severity of the invalid block. Full nodes that store a complete copy of the blockchain are known as **archival nodes.**

_How do Full nodes verify whether a transaction is valid?_

A full node will check whether all of the inputs in that transaction are unspent. This is made easier with a feature in Bitcoin called a **UTXO list. **The UTXO list is an indexed list of all unspent TXOs. The UTXO list is different to the confirmed database of transactions, the blockchain.

**Pruned Nodes**

If you can imagine, storing a database with millions of transactions will cost a lot in terms of storage space. Upwards of 150GB. Because of this, there is a feature to delete older data until your database is a certain storage size. If you can only afford to have 100GB, then older data will be deleted until your database is 100GB. A Full node that does this is known as a **pruned node.**

_Can a pruned node, still validate transactions?_

Yes, although a pruned node has deleted some percentage of their previous transactions. They have not deleted the UTXO list, which is what is used to verify whether a transaction is valid or not. A pruned node, can therefore still be classified as a full node. The UTXO list is _usually_ no more than 5-10GB in storage.

_Why does the archival node store the whole blockchain, when all that is needed is the UTXO list?_

Imagine a situation where another person, wanted to join Bitcoin. How would they know the current state of the database? They would need to download it, and it can be downloaded from a archival node.

_What if the archival node sends the newcomer a tampered database?_

The Bitcoin software used to download the database, does not trust anybody. When a new node downloads the database from an archival node, the software checks every transaction to make sure that they are all valid starting from the first transaction ever transacted on Bitcoin. Furthermore, any node that operates with a tampered database, will be excluded by the others. Remember, in the network no-one is trusted, if a full node receives data from another node, it is always validated against their own database and UTXO list.

**Lightweight Nodes**

_What If you want to use the capabilities of Bitcoin on a mobile device?_

Because mobile devices do not have hundreds of GBs of storage. They cannot run a Fully Validating Node. They also most of time cannot run a pruned node either, due to the size of the UTXO list. Furthermore, currently the Bitcoin software only allows archival nodes to convert to being a pruned node. So the mobile would have to become a full node and then convert.

The other option which is **not completely** **trustless **is a **lightweight node** or a **SPV node** or a **thin client**. Lightweight nodes connect to full nodes _that publicly advertise that they are lightweight node compliant, and instead of downloading the whole database, they only download the summary of each batch of transactions, also known as the metadata. In later chapters, we will call this the Block header._

Lightweight nodes send the full node that they have connected to, a filter. This filter tells the full node, what transactions they should send to the lightweight node. The full node will send you the transactions that you are interested in, and enough information for you to **verify** that **your transaction was validated. Since lightweight nodes do not hold a copy of the UTXO list, they cannot verify that they are not being given false information from the node they have connected to. In this case, lightweight nodes usually connect to multiple full nodes incase they are being deceived by one.**

