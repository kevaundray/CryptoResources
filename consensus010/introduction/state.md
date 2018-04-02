# Assumptions

# Deterministic Protocols

# Randomised Protocols

Here I explain what a deterministic algorithm is and why we need it in a consensus algorithm. Technically speaking.

# Timing Models

When discussing distributed models, we must make reasonable assumptions about time. These assumptions can be categorised into three headers, network, process and clock assumptions.

Network assumptions are assumptions you make on how long it will take for a message to reach the receiver.

Process assumptions are assumptions you make on how long it will take to make a computation

Clock assumptions are assumptions on how fast the clock times between computers will drift. If a clock in a computer is not synced up to some central time, then over time it will drift.

### Asyncronous Models

* No assumptions are made on how long a message will take

* No assumptions on computation

* No assumptions on clock drift

There are no bounds. No syncronisation.

### Syncronous models

* There is a bound on the latency

* Bound on the computational time

* Bound on the clock drift rate

In a system that uses a sync timing model, if there are k nodes, we can reach consensus with k-2 nodes crasing. This is because if a node does not reply within the bounded time, then we can assume it crashed and exclude it from the consensus. Consensus is trivial with 1 node as there is no-one to agree with.

### Partial asyncronous models

### FLP Impossibility Result

In computer science, there is a result known as FLP impossibility result, that states that a **deterministic** consensus protocol cannot have liveliness, safety and fault tolerance in an **asynchronous** system. It can have two at maximum. In other words, it is impossible to reach consensus in a **fully asynchronous system** using a** deterministic consensus protocol** if even **one node** is **faulty.** There are many ways to circumvent this theory:

* Instead of using a deterministic consensus protocol, we can use a randomised consensus protocol
* Instead of using a fully async model, we can use a partially async model or a sync model or make some sync assumptions
* Use a fault detector to detect the faulty nodes

**Randomised protocol**

Common coin, terminates with probability approaching one, similar to bitcoin, block consensus approaches one

