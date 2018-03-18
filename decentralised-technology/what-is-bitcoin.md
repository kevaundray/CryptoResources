# What Is Bitcoin?

Bitcoin uses blockchain technology, so a distributed decentralized database, in order to keep track of everyones 'accounts' and transaction history. Bitcoin uses a Peer to Peer network, so that each person on the Bitcoin network can communicate with each other, making sure that their databases are identical.

This chapter will assume that you have some understanding of bitcoin already. The purpose of this chapter is to solely outline the bitcoin protocol, so that we can dive into the more technical aspects of Bitcoin.

First let's forget about a Bitcoin for a moment.

Let's assume that we want to send an image over the internet, and the image is only allowed to be sent once.

How can we assure this?

A centralised solution would be to have a list somewhere that is guarded by a company and in order to send an image, you must tell the company who you are sending it to and what image it is. Before you send it, the company checks to see if you have sent that image to someone else before and that you also own the image.

If the company becomes corrupt, then you have no way of proving, that images are in fact yours. The same principle applies if they get hacked. The hacker could transfer all ownership of the images to themselves.

The list is clearly needed to track ownership, the problem is that if only one person has it, then that one person is suddenly God and he can do whatever he wants and if something happens to that one person, then your information can be modified. So what if everyone had the list? What if instead of one company checking and verifying each images ownership, we all did?

Now replace the word 'image' with 'digital money' or with 'Bitcoin'.

_What if someone tries to change their list?_

The information would only be changed on their list and they would need to change it on everyone else's database also. If they do give themselves 100 Bitcoins, then when they attempt to send it to someone else for a service or product, they will then check their database and see that this person does not have 100 Bitcoin's, according to _their_ database.

Now that everyone has a copy of the list. How do we all agree on the general state of the list? There could be friends who are not really friends and they may decide to send two copies simultaneously to two different people, who really owns the picture now, person A or person B? Remember, everything is done over the internet and you don't want to phone up all of your friends each time to see if someone also sent them an image. It would become even more arduous if you did not know the people you were sending to.

In other words, how do we reach consensus, a general agreement, on the state of everybodies lists?

You may answer, what if someone is elected to add to the list based on some sort of rules. That is a good idea. These rules must be baked into Bitcoin and cannot be changed. If they are changed, then we no longer have Bitcoin, more on hard forks in a later chapter. These rules that will allow someone the right to append to everyones database, will be called the _consensus rules. _ 

The consensus rules should work so that this person changes periodically. We should also not wholly believe what they tell us. We will verify ourselves that what they are writing is valid, if not we reject their data.If we verify and they did a good job, the majority of the network says they did a good job, then the network should reward them.If we verify and they did a bad job, or tried to cheat, then the network should punish them.The incentives of the elected, align perfectly with the interest of the network.

