Notes:

This book will normally begin with a high level explanation of each topic, then a medium to low level explanation. This is so that there is a transition between topics for users

Bitcoin is like 'Lord of The Flies'

Philosophical chapter on blockchain - Problems with central authority

Blockchain business use cases - Ask yourself, is there an element of trust needed?

Who regulates Bitcoin?

If Bill gates or Warren Buffet or The President of America went into Bitcoin, how much power would he have?

What is the objective of bitcoin?

Is Bitcoin actually decentralized?

What is the difference between a blockchain and bitcoin?

How do we shut down bitcoin?

Is Bitcoin neutral?

Can Bitcoin scale?

Can we have bitcoin without currency?

Let's suppose Alice wants to send money to Bob.

How would she do this?

She could meet up with Bob and give him his $5. In this scenario, she will first verify that it is Bob, by looking at him. She will then give the money over to Bob and Bob will acknowledge that he did receive the money. If Alice goes into her pocket and tries to give Charlie the same $5, well she can't, because she just gave it to Bob. Ownership of _that_ $5 has been transferred to Bob.  
In this scenario, it would be silly for Alice to meet Bob and video record it all for her bank to then verify. This in-person transaction did not need a third party.

Doing the same thing online however, is difficult. Without a third party in between. If I sent any digital asset, it would be difficult to track whether I did not send it to someone else first. To test this out, send your friend an image. Now send a different friend the same image. Both friends have no idea, whether you sent that image to someone else and so have no idea, if you still own the image.

What if we decided to make a public database, that everyone can see and whenever a transaction was made, we write it in this public database that everyone can see. This sounds like a good idea, what happens if this database gets hacked? Then we will not know who owns what. We could have an organization guard it and verify transactions for us, however our objective is to move away from central authorities and banks.

What if everyone had the database? There is no longer a single point of failure. The database is now distributed.

How does each node know about each other and each transaction?  
Using a Peer to peer network ...

// another throwaway possibly

**The Byzantine Generals Problem**

_Please note that the Two Generals Problem is unsolvable, while the Byzantine Generals Problem which is a generalisation is solvable._

10 generals want to attack a city. If they both do it at the same time, they will be able to take the city. If they do not co-ordinate their attack then the city will defeat them. The problem lies in that five generals are on one side of the city, and five on the other. Using a messenger, they need a send a message to the other side agreeing on a date and time to storm the city. The messenger has to go through the city in order to deliver the message, and as there is a chance that the message could be corrupted, the messenger cannot be trusted. How can these generals agree on a time and date using the messenger?

So the blockchain uses consensus algorithms to elect the next person who will add to the next block.

_Another analogy for transactions, is that it is a game of lock and unlock. I will lock up these funds with your public key, you can unlock it and put another lock on it to someone elses public key._

_Bitcoin uses blockchain technology, so a distributed decentralized database, in order to keep track of everyones 'accounts' and transaction history. Bitcoin uses a Peer to Peer network, so that each person on the Bitcoin network can communicate with each other, making sure that their databases are identical._



Missed out mining pool.

Sequence number

ScriptTOHash

ExtraNonce



