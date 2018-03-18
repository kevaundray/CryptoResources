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



This chapter will assume that you have some understanding of bitcoin already. The purpose of this chapter is to solely outline the bitcoin protocol, so that we can dive into the more technical aspects of Bitcoin.

First let's forget about a Bitcoin for a moment.

Let's assume that we want to send an image over the internet, and the image is only allowed to be sent once.

How can we assure this?

A centralised solution would be to have a list somewhere that is guarded by a company and in order to send an image, you must tell the company who you are sending it to and what image it is. Before you send it, the company checks to see if you have sent that image to someone else before. When someone receives the image, they also alert the company.

If the company becomes corrupt, then you have no way of proving that images are in fact yours. The same principle applies if they get hacked. The hacker could transfer all ownership of the images to themselves.

The list is clearly needed, the problem is that if only one person has it, then that one person is suddenly God and he can do whatever he wants. So what if everyone had the list? What if instead of one company checking and verifying each images ownership, we all did?

Now replace the word 'image' with 'digital money' or with 'Bitcoin'.

_What if someone tries to change their list?_

The information would only be changed on their list and they would need to change it on everyone else's database also. If they do give themselves 100 Bitcoins, then when they attempt to send it to someone else for a service or product, they will then check their database and see that this person does not have 100 Bitcoin's, according to _their_ database.

_What actually happens when I send 2 Bitcoins to Alice?_

Alice verifies that you indeed have that two Bitcoins to send. She then puts the transaction in a 'pending' state and other users will try and verify this pending state

_What if someone does have 1BTC and they simulateneously send it to two other people?_

