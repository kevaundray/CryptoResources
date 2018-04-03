# Distributed And Decentralised Systems

_Not suitable for consumption - needs to be cleaned up_

#### Distributed Systems

The definition for what a distributed system is will change depending on the person you are asking.

The author will use the following definition for the remaining of the book:

> A distributed system is a system that has some set of computers, that are connected to each other via a network. The goal of a distributed system is to make the network work as if it were a single node to the external users.

* If one computer fails within a distributed system, then it should not affect the other computers. Failure is not propagated.
* Time is not shared
* concurrent processing

#### Decentralised Systems

##### Politically Decentralised Systems

> A politically decentralised system is one that has no central authority. No one individual or organisation can control the system.

##### Architecturally Decentralised Systems

> An architecturally decentralised system is similar to a distributed system, in that it is a system with no central geographical location and can therefore tolerate the failure of some amount of physical computers on the network. How is the network connected?

##### Logically Decentralised Systems

> A logically decentralised system is one that has no central location for the logic of the system. A logically decentralised system will behave like a single machine and have one shared state.

_The definitions for a decentralised system are referenced from Vitalik Buterin: _[https://medium.com/@VitalikButerin/the-meaning-of-decentralization-a0c92b76a274](https://medium.com/@VitalikButerin/the-meaning-of-decentralization-a0c92b76a274)

The goal of a distributed decentralised system is for every participating node to arrive at the same state.

With a distributed system it is more about the **where **is the process being done

With a centralised and decentralised network, the question is a **who **, as in who is authorising the processes.

Centralised distributed: One node is authorising the calculations and the result is delivered to him. Sort of like a master slave definition.

Decentralised distributed: No single authority authorises the calculation, the results are shared upon each node.

If you can point to a single person in the network or minority organisation who has the authority to initiate a process, then it is not politically decentralised.

If you can point to a set of logical rules in the source code that are needed in order for nodes to interact, then the system is not logically decentralised.

With all things it is not always a simple black and white picture, all blockchains can be seen as politically decentralised because at the end of the day, one person or minority organisation could potentially decide to change the source code without your authority. You of course do have the choice to move to a new blockchain fork with those who agree with you, taking your money to this new blockchain, it is more decentralised than your bank where if they change something or decide to take your money, you have no choice. So I would like to argue that complete decentralisation is not entirely possible, there will be some components of a system that is centralised and as a whole one system can be more decentralised than another. It is a scale.

