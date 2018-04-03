# Faults and Failures

_Not suitable for consumption_

Nodes on a distributed system may experience faults at any moment, so there must be some way to continue without these faulty nodes.

Examples of such faults:

* Crashing
* Crashing and Looping \(_Happened to Bitcoin when they changed the database provider_\)
* Ddos
* Corruption of data
* Bug in Code
* Hacked
* Hardware problem
* Accidental deletion of software
* Packets never arrive
* System has lost internet connection

When building distributed systems it is important to account for the possible failures that a node or the whole network may experience.

### Network Failures

When dealing with networks on a decentralised system, your goal when communicating with another node, is to either deliver information or receive information. Therefore most network failures, can be solved by using TCP/IP and SSL. _This book will mostly be going over the node failures. The other type of network failure not covered by TCP/IP and SSL is partitioning._

~~_Note that TCP only covers point to point, not broadcast. There are good algorithms out there that allow for sufficient broadcast coverage. Datalink protocols can convert unreliable links to reliable links. _~~

~~_May include reliable broadcast and atomic broadcast_~~

### **Node Failures**

There are seven main types of node failures. The less severe is known as fail-stop and the most severe is known as byzantine. The most severe failure covers the less severe types of failures except the least severe and so we will only cover the least severe and the most severe.

#### Fail-Stop

If a node fails and stops communicating with the rest of the network. Then it has **failed** and **stopped.** For example, the node crashes or the node is experiencing hardware problems. When a node fail-stops, the network immediately knows which node has stopped working. This can be done through a failure-detector in each node for example.Therefore, one **assumption** that can be made with fail-stop failures, is that we know which node has stopped working, when it has stopped.

**Checkpoint/Restart**

One solution for fail-stop failures, is to take regular checkpoints of the system and when the node fails. You reboot the system to the last good checkpoint. This is assuming that it is not a hardware problem.

#### **Byzantine Failures**

Byzantine failures are failures that do not cause the node to crash. Byzantine failures are the most severe types of failures in a distributed system because although they do not halt the machine, they can propagate false information and collude with other nodes experiencing byzantine failures. Byzantine failures encompass a lot of the other types of failures that we have not mentioned, so we cannot be sure what it happening with the machine.

One example of a byzantine failure is corruption of data upon transmission. This will not cause the node receiving it to stop, but will result in incorrect calculations and depending upon the system, this could be catastrophic.

Another example of a byzantine failure, is mismatched software versions; if one node is running on version one and the other node is running on version two, then when they communicate, the node running version one will be sending invalid messages to the other node.

Nodes that exhibit byzantine failure behavior are known as **traitor nodes, ** and cannot be trusted by the rest of the network.

Unlike fail-stop, with byzantine failures, we cannot make any assumptions because nodes that exhibit byzantine failures can also function as normal to other nodes. One example of this is if a node is hacked and the hacker programs the node to send good information to some nodes and incorrect information to others.

