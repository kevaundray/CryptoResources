# **Overview of Bitcoin**

_This section serves as a primer, to understand the Bitcoin protocol, and will not include all information for each component of Bitcoin. These will be included in the Deep Dive sections._

This chapter will assume that you have some understanding of bitcoin already. The purpose of this chapter is to solely outline the bitcoin protocol, so that we can dive into the more technical aspects of Bitcoin, step by step.

Let's assume that we want to send an image over the internet, and the image is only allowed to be sent once.

_How can we assure this?_

A centralised solution would be to have a database that is guarded by a company and in order to send an image, you must tell the company who you are sending it to\(recipient\) and what image it is\(Image Identifier\). Before you send it, the company checks to see if you have sent that image to someone else before and that you also own that image.

If the company becomes corrupt, then you have no way of disputing which images are yours, since all information was kept on their database. The same principle applies if they get hacked. The hacker could transfer all ownership of the images to themselves or delete the database entirely.

The database is clearly needed to track ownership, the problem is that if only one person or company has it, then that one person is suddenly God-like and he can do whatever he wants and if something happens to that one person, then your information can be modified. So what if everyone had the list? What if instead of one company checking and verifying each images ownership, we all did?

Now replace the word 'image' with 'digital money' or with 'Bitcoin'.

_How are lists updated?_

When someone sends a Bitcoin to another person. They alert the whole network as to whom they have sent it to and each person, checks that this is a valid transaction before they alter their own list.

_What if someone tries to change their list to benefit them, to make themselves rich?_

The information would only be changed on their list and they would need to change it on everyone else's database also. If they do give themselves 100 Bitcoins, then when they attempt to send it to someone else for a service or product, the receiver will then check their database and see that this person does not have 100 Bitcoin's, according to _their own _database.

Now that everyone has a copy of the list. _How do we all agree on the general state of the list?_ There could be friends who are not really friends and they may decide to send the same Bitcoin simultaneously to two different people, who really owns the Bitcoin's now, receiver A or receiver B? Remember, everything is done over the internet and you don't want to phone up all of your friends each time to see if someone also sent them 2 Bitcoins too. It would become even more arduous if you did not know the people you were sending to. This is the case with Bitcoin.

In other words, how do we reach consensus, a general agreement, on the state of everybodies lists?

You may answer, what if someone is periodically elected to check and add to the list based on some sort of rules. These rules however must be baked into Bitcoin and cannot be changed. If they are changed, then we no longer have Bitcoin. _This is known as a hard fork and will be added into the book in later editions_. These rules that will allow someone the right to _append_ to everyones database, will be called the _consensus rules. _

We should also not wholly believe what they tell us. We will also verify ourselves that what they are writing is valid, if not we reject their data.If we verify and the majority of the network says they did a good job, then the network should reward them.If we verify and the majority say they did a bad job, or tried to cheat, then the network should punish them.Therefore, the interest of the elected, align with the interest of the network. _The network decides on whether the job is "good" by referring to the consensus rules defined in the code, no ambiguity is present._

To make this persons job more convenient, instead of verifying one transaction, he will verify batches of transactions.

_How does this stop someone from sending to two people simultaneously?_

Now when someone sends a transaction, it gets put into a pool or a list of unconfirmed transactions. To become elected you must take as many transactions as the _rules_ says you can take, from this list of unconfirmed transactions. You then check each transaction to verify that each transaction is valid and there are no conflicting transactions like the same person spending the same amount of Bitcoin's twice. If you leave that transaction in, you will be punished by the network, if you take it out you could _potentially_ get a reward. Once you have finished checking you must then do some work and only then will you be elected, if you were the fastest to complete the work.Note that just like every other race for election, there is more than one candidate and only one can be elected periodically. _This is why we say potentially get a reward. More on this in Deep Dive: Mining._

_What is this work that the elected person does?_

When we referred to the network punishing the elected person for doing wrong, we meant economically. When you verify that all transactions in your batch of transactions are good, you must append a number to the end of the data and hash it, until you get some numerical pattern in the output. This process is computationally intensive and will incur electricity, which is not free. If you include a bad transaction or you do not do everything according to the rules, then you will have incurred electricity cost for nothing, as the majority of people who verify your batches of transactions, will reject it as it does not follow the consensus rules, and thus you will be punished economically.

_Note: Hashing was covered in a previous chapter._

_Why is this hashing part important?_

Without the hashing, then the person elected will have nothing to lose. There will be no punishment in not following the rules, no electricity cost, and so no incentive to _not_ include the bad transactions. The hashing also provides a way to make the block immutable. If information inside of the block is changed, then the block becomes invalid. This is because as soon the information changes, the pattern we described earlier would change.

This was a medium level overview of bitcoin. In the deep dive sections, we will answer possible unanswered questions such as:

_How does the person elected get his reward?  
Who originally decides on the consensus rules?_

_Who decides on the pattern for the hash output?_

_Where is this pool of unconfirmed transactions?_

_Let's say that someone wanted to join this 'network', they would have to download all of the information from somewhere. What's to say that the person they download it from, has not corrupted the fifth batch in the database to make themselves rich. Doing this would mean that I would receive Bitcoins from them, when in fact they do not have any Bitcoins. How is this prevented?_

