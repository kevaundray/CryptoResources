# Assumptions

_Not suitable for consumption_

In order to compose proofs or be certain of things, we must make assumptions about our model. We then build protocols around our assumptions, if our assumptions were to be invalidated, then anything that was built upon the assumption will also be invalid.

A quick example:

We are trying to reach consensus on how many people are over the age of 30?

If I have a distributed system that just counts up the amount of people that are over 30 years old. So what happens is a client connects to the system and it asks "Are you over 30?" The client types enters "Yes" and the result is summed up.

What assumptions have we made and are they weak or strong?

we have assumed that the client speaks english. What if they enter "Si" ? How will our system react to this? Let's say it does not crash, then it is byzantine failure and we have no idea how it will affect the system.

How do we strengthen our assumption so that this assumption will start to hold up in most cases?

* Some way, only allow the client to enter YES or NO
* Language converter
* If we do not see a yes or no, the system should crash and we see that we can actually convert a byzantine fault into a fail-stop. The customer may not like it, and some systems do believe that if something is wrong, the system should just crash and not propagate any false information. Some others think we should fail-silently, which comes with it's own errors that we will not be discussing.

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

Consensus cannot be reached if 1 node crashes; impossibility result.

### Syncronous models

* There is a bound on the latency

* Bound on the computational time

* Bound on the clock drift rate, upper and lower

In a system that uses a sync timing model, if there are k nodes, we can reach consensus with k-2 nodes crashing. This is because if a node does not reply within the bounded time, then we can assume it crashed and exclude it from the consensus. Consensus is trivial with 1 node as there is no-one to agree with.

### Partial asyncronous models

* starts off as async, but eventually behaves like sync

In a system with partial async, if we have k nodes, we can reach consensus if less than k/2 nodes crash.

### Timed asyncronous models

* No assumptions are made on how long a message will take

* No assumptions on computation

* Clock drift rate is known

### 



