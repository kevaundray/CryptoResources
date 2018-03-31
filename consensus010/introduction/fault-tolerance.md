# Byzantine Fault Tolerance

_Not suitable for consumption_

For a decentralised network to have byzantine fault tolerance, it must be able to deal with byzantine failures.

To do this, the network comes to a **consensus** on which node is faulty and exclude it from the network. With byzantine failures, we cannot make any assumptions however. We have just assumed that only **one** node is faulty. It could be the case that more than one node is faulty. So How do we reach consensus when one node is faulty? How do we reach consensus when more than one node is faulty? How many nodes can be seen as traitors before we cannot reach consensus?

In practice, the above scenario is impossible and in order to build a system, we must make some assumptions. These assumptions have to be strong and impractical to realise. If any of the assumptions are broken, then the consensus algorithm used to combat the byzantine failures, will not be byzantine fault tolerant anymore and will open the network up to attack vectors.

##### 



