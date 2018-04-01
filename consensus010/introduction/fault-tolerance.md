# Fault Tolerance

_Not suitable for consumption_

For a decentralised network to have fault tolerance, it must be able to deal with byzantine failures and fail-stops.

To do this, the network must come to a **consensus** on which node has failed and exclude it from the network. If the failure is a fail-stop, then the network knows which node has failed and can put in place the proper measures to continue operating without that node, until it comes back online or if it comes back online.

With byzantine failures, we cannot make any assumptions however. We cannot assume that only **one** node is faulty. It could be the case that more than one node is faulty. So How do we reach consensus when one node is faulty? How do we reach consensus when more than one node is faulty? How many nodes can be seen as faulty or traitorous before we cannot reach consensus?

In practice, we must make some assumptions. These assumptions have to be _strong_ and _impractical_ to realise. If any of the assumptions are broken, then the consensus protocol used to combat the byzantine failures, will not be byzantine fault tolerant anymore and will open the network up to attack vectors.

# Liveliness

Another desirable feature of a decentralised network, is liveliness. A decentralised network can guarantee liveliness, if all non-faulty nodes can eventually produce a value in the network and not get _stuck_. There is no time limit in this case.

# Safety

Safety is another property of a consensus protocol. If a consensus protocol can guarantee safety, then all non-faulty nodes that are following the rules of the network, should produce the same valid output. For example, given 10 nodes, if you were to give them all the same set of inputs and told them to follow the same set of instructions on how to process the input, then they should all arrive at the same output \(state\). The outputs must be valid according to the rules. If you are familiar to put this into blockchain terminology, a network is safe, if the chain does not fork.

