# Byzantine Fault Tolerance

_Not suitable for consumption_

For a decentralised network to have byzantine fault tolerance, it must be able to deal with the byzantine failures that can be exhibited by the network. The network must come to a **consensus** on which node is faulty and exclude it from the network. With byzantine failures, we cannot make any assumptions however. We have just assumed that only **one** node is faulty. It could be the case that more than one node is faulty. How do we reach consensus when one node is faulty and furthermore, how do we reach consensus when more than one node is faulty? How many nodes can have byzantine failures before we can reach consensus? In other words, how many nodes can be seen as traitors before we can reach consensus?

The above scenario is impossible and in order to build a system, we must make strong assumptions. If any of the assumptions are incorrect, then the algorithm used to combat the byzantine failures, will not be byzantine fault tolerant.

The remaing chapters of this book will inform the reader, on the consensus algorithms used in cryptocurrency that allow the system to have byzantine fault tolerance.



**The author would like to include the two generals problem, the byzantine generals problem and the runtime for BGP.**

Practical BFT was introduced as a solution for BGP, which is derived from Two generals.

PBFT 

