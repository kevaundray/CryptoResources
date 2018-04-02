# State

One important aspect and challenge of a decentralised distributed network, is to ensure that every node in the network arrives at the same state. Put another way, all nodes in the network should all agree on the state of the network. The state should only change according to some set of rules, and once the state has changed then all nodes should eventually agree on the new state, a globally consistent shared state.

In systems such as Bitcoin and Ethereum, the state is the **blockchain. **The set of rules that allow the blockchain to change are called the **consensus protocol.**

Along with ensuring that the network arrives at a globally consistent shared state, a consensus protocol must also deal with byzantine failures and fail-stop failures. In the following chapters, we will formalise some of the terms discussed in this section and discuss properties of a consensus protocol.

**The author would like to add an example using graphs, however he would not like to generalise as some graph implementations vary.**

# Deterministic Protocols

# Randomised Protocols

Here I explain what a deterministic algorithm is and why we need it in a consensus algorithm. Technically speaking.

# Timing Models

When discussing distributed models, we must make reasonable assumptions about time. These assumptions can be categorised into three headers, network, process and clock assumptions.

Network assumptions are assumptions you make on how long it will take for a message to reach the receiver.

Process assumptions are assumptions you make on how long it will take to make a computation

Clock assumptions are assumptions on how fast the clock times between computers will drift. If a clock in a computer is not synced up to some central time, then over time it will drift. 

# Asyncronous Models

* No assumptions are made on how long a message will take 
* No assumptions on computation
* No assumptions on clock drift

There are no bounds. No syncronisation.

# Syncronous models

* There is a bound on the latency
* Bound on the computational time
* Bound on the clock drift rate

# Partial asyncronous models



