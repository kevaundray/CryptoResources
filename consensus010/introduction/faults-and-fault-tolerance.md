# Faults and Failures

_Not suitable for consumption_

Nodes on a decentralised system may experience faults at any moment.

Examples of such faults:

* Crashing
* Crashing and Looping
* Ddos
* Corruption of data
* Bug in Code
* Hacked
* Hardware problem
* Accidental delete
* Packets never arrive
* System has lost internet connection

When building decentralised system it is important to account for the possible failures that a node or the whole network may experience.

### Network Failures

When dealing with networks on a decentralised system, your goal when communicating with another node, is to either deliver information or receive information. Therefore most network failures, can be solved by using TCP/IP and SSL. _This book will mostly be going over the node failures. The other type of network failure not covered by TCP/IP and SSL is partitioning. These may not be discussed in this book, unless a consensus algorithm deals with it._

TCP/IP guarantees one to one or point to point guarantees. In a distributed network, we need to communicate with a group of nodes, how do we guarantee successfull message. delivered to everyone in the group? Atomic broadcast is a solution, so an algorithm that says deliver to all or deliver to none. Relaying

### **Node Failures**

There are seven main types of node failures. The less severe is known as fail-stop and the most severe is known as byzantine. The most severe failure covers the less severe types of failures and so we will only cover the least severe and the most severe.

#### Fail-Stop

If a node fails and stops communicating with the rest of the network. Then it has **failed** and **stopped.** For example, the node crashes or the node is experiencing hardware problems. When a node fail-stops, the network immediately knows which node has stopped working. One **assumption** that can be made with fail-stop failures, is that we know which node has stopped working.

**Checkpoint/Restart**

One solution for fail-stop failures, is to take regular checkpoints of the system and when the system fails. You reboot the system to the last good checkpoint. This is assuming that it is not a hardware problem.

#### **Byzantine Failures**

Byzantine failures are failures that do not cause the system to stop. Byzantine failures are the most severe types of failures in a decentralised system because although they do not halt the machine, they can propagate false information.

One example of a byzantine failure is corruption of data upon transmission. This will not cause the node receiving it to stop, but will result in incorrect calculations and depending upon the system, this could be catastrophic.

Another example of a byzantine failure, is mismatched software versions; if one node is running on version one and the other node is running on version two, then when they communicate, the node running version one will be sending invalid messages to the other node.

Nodes that exhibit byzantine failure behavior are known as **traitor nodes, ** and cannot be trusted by the rest of the network.

Unlike fail-stop, with byzantine failures, we cannot make any assumptions up on the network, as nodes that exhibit byzantine failures can also function as normal to other nodes. One example of this is if a node is hacked and the hacker programs the node to send good information to some nodes and incorrect information to others.

