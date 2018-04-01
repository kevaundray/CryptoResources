# Byzantine Generals Problems

_Not the Two Generals Problem, which is unsolvable._

The Byzantine generals problem is often used to represent the scenario of byzantine faults.

The Byzantine Generals goes as folllows:

> A group of generals wish to make a decision on whether to attack a city or retreat. In order to win, all generals must decide to attack the city. Therefore all generals must either decide on whether they want to attack or retreat. The generals are situated at different locations around the city and so they use messengers to communicate with each other. There is also a possibility that some of the generals are traitorous and will use a voting strategy that ensures that the city wins.\]
>
> For example, If there are five generals. and two generals vote to attack, then two generals vote to retreat. The traitor general will tell the ones that voted to attack, that he would also like to attack, and the ones that voted to retreat that he would also like to retreat. With this, the two generals that voted to attack will attack the city with the assumption that the decision was Attack,Attack,Attack,Retreat,Retreat.

**How is this analogous to Byzantine failures?**

It is impossible to assume which general is a traitor. Similarly, it is impossible to assume which node is a trator node.

The goal of the Byzantine generals, is to reach consensus on whether to attack or retreat in face of the fact that there are traitors in the ranks. Similarly, a system that is Byzantine fault tolerant achieves consensus even when there are nodes that are actively trying to destroy the system.

We are implicitly assuming that the messenger will arrive to the other generals with the message. If this assumption was not made, then we would have the _Two Generals Problem, _ which is unsolvable.

**A solution to the Byzantine generals problem is also byzantine fault tolerant.**

**The author would like to include the two generals problem, the byzantine generals problem and the runtime for BGP.**

**The two generals problem may not be needed, however it does bring to light the assumption that we have to assume that message delivery is somewhat reliable.**

Practical BFT was introduced as a solution for BGP, which is derived from Two generals.

PBFT

