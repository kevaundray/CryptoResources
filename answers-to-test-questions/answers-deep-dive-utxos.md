# Answers - Deep Dive: UTXOs

**1\) **_Alice has now received 1 Bitcoin, from her transaction with Bob. She would like to now send Kate, 0.5BTC for a new phone and Nicole 0.2BTC for a new computer. Describe the process for this transaction._

\_\*\*Depending upon your knowledge thus far, there are two answers to this question. We will discuss both of them.

Scenario 1: Alice sends it to both of them in one transaction. \*\*\_

\_I have made no mention to being able to send to multiple people at once, and this may not have necessarily been intuitive.

**Alice uses her 1BTC and sends 0.5BTC to Kate, 0.2BTC to Nicole and sends 0.3BTC back to herself as change.**

Scenario 2: Alice sends it to each of them in seperate transactions.  
**Alice uses her 1BTC and sends 0.5BTC to Kate. She receives 0.5BTC as change.  
Alice uses her 0.5BTC and sends 0.2 BTC to Nicole. She receives 0.3BTC back as change.**

**2\) **True or False: Only UTXOs can be used as inputs to transactions

True. A UTXO is an unspent transaction output. If you attempt to spend a transaction output that you have already spent, then the elected person we mentioned in the _'overview of bitcoin' _ will reject the transaction.

