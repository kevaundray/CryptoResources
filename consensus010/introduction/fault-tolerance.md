# State

One important aspect and challenge of a decentralised distributed network, is to ensure that every node in the network arrives at the same state. Put another way, all nodes in the network should all agree on the state of the network. The state should only change according to some set of rules, and once the state has changed then all nodes should eventually agree on the new state, a globally consistent shared state.

In systems such as Bitcoin and Ethereum, the state is the **blockchain. **The set of rules that allow the blockchain to change are called the **consensus protocol.**

Along with ensuring that the network arrives at a globally consistent shared state, a consensus protocol must also deal with byzantine failures and fail-stop failures. In the following chapters, we will formalise some of the terms discussed in this section and discuss properties of a consensus protocol.

**The author would like to add an example using graphs, however he would not like to generalise as some graph implementations vary.**

# Fault Tolerance

_Not suitable for consumption_

For a consensus protocol to have fault tolerance, it must be able to deal with byzantine failures and fail-stops.

If the failure is a fail-stop, then the network knows which node has failed and can put in place the proper measures to continue operating without that node, until it comes back online or if it comes back online. With the exclusion of that node, the system can come to a consensus on the state.

With byzantine failures, we cannot make any assumptions however. We cannot assume that only **one** node is faulty. It could be the case that more than one node is faulty. So How do we reach consensus when one node is faulty? How do we reach consensus when more than one node is faulty? How many nodes can be seen as faulty or traitorous before we cannot reach consensus?

In practice, we must make some assumptions about the faults. These assumptions have to be _strong_ and _impractical_ to realise. If any of the assumptions are broken, then the consensus protocol used to combat the byzantine failures, will not be byzantine fault tolerant anymore and will open the network up to attack vectors depending on the assumption that was broken.

##### What happens when a network uses a consensus protocol that does not have fault tolerance?

For example, In Bitcoin the assumption is made that it is impractical for 51% of the network's hashing power to be controlled by a malicious node or multiple malicious nodes colluding. This assumption is impractical in practice because to own 51% or more of the networks hashing power is expensive and the network would become aware of the large orders for specific hardware parts.  If the malicious node is able to take control of 51%+ of the network then the assumption would be broken and the party would then be able to initiate a double spend attack.

# Liveliness / Termination

A consensus protocol can also have a property known as liveliness. A consensus protocol can guarantee liveliness, if all non-faulty nodes can eventually produce a value in the network and not get _stuck_. There is no time limit in this case and so we must use time models to determine appropriate response times.

##### What happens when a network uses a consensus protocol that does not have liveliness or is not 'live'?

Without liveliness, a node can run the protocol algorithm in hopes to transition to a new state and get stuck. In Bitcoin, the node could be at some block, then upon receiving a new block it gets stuck trying to validate the block due to the block version changing. In this case, there is no more information that this node could receive that would allow it to get _unstuck._

# Safety

If a consensus protocol can guarantee safety, then all non-faulty nodes that are following the rules of the network, should produce the same valid state For example, given 10 nodes, if you were to give them all the genesis block, the first block in any blockchain based system, then they should be able to validate and build the blockchain themselves and come to the same state as the rest of the network. The state must also be valid according to the consensus protocol.

_**Talk about safety meaning agreement and validity**_

Agreement: All non-faulty nodes must choose the same value

Validity: The output value is valid by the consensus protocol.

##### What happens when a network does not have safety or is not 'safe'?

When a blockchain is not _safe_, the network will frequently experience block forks, where some nodes in the network think that their version of the blockchain is correct, while another set think they are looking at the one true blockchain.

# 



