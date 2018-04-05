# Ripple Consensus Protocol

## The author is considering doing a ripple course?

## 

## Short Summary

The user submits a transaction to a validator

## Longer Summary

Outlining the definitions made by the ripple consensus white paper:

**Server**: A server is any entity running the Ripple Server software \(as opposed to the Ripple Client software which only lets a user send and receive funds\), which participates in the consensus process.

_This means that if you would like to use the ripple network to send funds, it is open in that sense. It is only permissioned, when discussing becoming a **validator**. A **server** in the ripple consensus paper will be seen as a validator. A normal user is not mentioned._

**Ledger**: The ledger is a record of the amount of currency in each user’s account and represents the “ground truth” of the network. The ledger is repeatedly updated with transactions that successfully pass through the consensus process.

**Last-Closed Ledger**: The last-closed ledger is the most recent ledger that has been ratified by the consensus process and thus represents the current state of the network.

**Open Ledger**: The open ledger is the current operating status of a node \(each node maintains its own open ledger\). Transactions initiated by end users of a given server are applied to the open 2 ledger of that server, but transactions are not considered final until they have passed through the consensus process, at which point the open ledger becomes the last-closed ledger.

**Unique Node List \(UNL\)**: Each server, s, maintains a unique node list, which is a set of other servers that s queries when determining consensus. Only the votes of the other members of the UNL of s are considered when determining consensus \(as opposed to every node on the network\). Thus the UNL represents a subset of the network which when taken collectively, is “trusted” by s to not collude in an attempt to defraud the network. Note that this definition of “trust” does not require that each individual member of the UNL be trusted \(see section 3.2\).

**Proposer**: Any server can broadcast transactions to be included in the consensus process, and every server attempts to include every valid transaction when a new consensus round starts. During the consensus process, however, only proposals from servers on the UNL of a server s are considered by s.

**Nonfaulty** **Node**: nodes in the network that behave honestly and without error.

**Validating A Transaction: ** Each node will be given a transaction  and they must decide on whether they think it is valid by assigning it a 0 or a 1. _This is similar to binary consensus._

_**C**_**orrectness:** means it is necessary for a distributed system to be able to discern the difference between a correct and fraudulent transaction. _**This is slightly different from the correctness property of a consensus protocol. Whereby correctness means liveness and termination.**_

**Agreement: **Refers to the problem of maintaining a **single global truth** in the face of a decentralized accounting system.

**Utility: **The  “usefulness” of a distributed payment system. This includes transaction time, computational power needed to participate in the network and technical proficiency required by the user to avoid being defrauded.

# Ripples Definition Of Consensus

1. \(C1\): Every nonfaulty node makes a decision in finite time

2. \(C2\): All nonfaulty nodes reach the same decision value

3. \(C3\): 0 and 1 are both possible values for all nonfaulty nodes. \(This removes the trivial solution in which all nodes decide 0 or 1 regardless of the information they have been presented\).

# Goal Of Ripple Consensus Algorithm

Achieve consensus at each ledger-close \(even if consensus is the trivial consensus of all transactions being rejected\), and that the trivial consensus will only be reached with a known probability, even in the face of Byzantine failures

# Explanation Of Algorithm

* A server receives transactions within a period of time, four seconds for example. This period will be called a round.



