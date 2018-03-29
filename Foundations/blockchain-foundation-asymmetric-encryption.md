# **Blockchain Foundation**

**Asymmetric Encryption**

**High-Level Explanation**

Imagine yourself in a room with a machine. You press a button on the machine then **two keys** along with a **box** appear.

After practicing with the **two keys** and **the box**, you notice three things:

* Whenever you **lock the box with key A**, key A can no longer unlock it. **You need key B to unlock it**.
* Whenever you **lock the box with key B**, **you need key A to unlock it**.
* One of the keys, _key B_, has a lot more cuts than the other. It looks more complicated.

Clearly, there is some connection between these two keys, you just don't know what it is. You try to check the cuts on the key to see if you could somehow go from one key to the other. You notice that **Key A can be derived from Key B**.

![](/assets/keys.png)

You press the machine again. This time only two keys come out. You try to lock the box with the new key, **key C. **It locks. You then try to open it with **key A**. No luck. You try **key B.** No luck. You try **Key D**, the key which came with **Key C** and the box opens again.

You realise that **whatever one key locks, only it's corresponding key can open**. You start to think of the things you can do with this. If you give your friend one of the keys, then have him lock something with it, then only you will be able to unlock it. Which key do you give him?  You decide to give him the key A, because if you give him Key B, then he could make **key A** from it.

What if your friend copies Key A? 

This means that you cannot be certain that what you lock with **Key B **will only be read by him.  This is because if your friend copies the other key and misplaces it, then the person who found the key would be able to open whatever you locked, if they got their hands on it. He may not tell you if this happens also. We have no choice, but to assume that the key you send your friend has been compromised. We will call this the **public key. **The one that you did not send and are keeping to yourself will be known as the **private key.**

_What can we do with the private key then?_

If you are the only person to have your private key, then you could use this to claim ownership of things. Similar to putting your PIN into an ATM to get your funds. The bank assumes that no-one else has your PIN and so when your pin is entered along with your card into an ATM, the bank can verify that it was you.

**No one has your private key** and so when you lock a box with a message inside of it, anyone who has the corresponding **public key ** can be sure that it was you who unlocked 

**Low-Level Explanation**

Asymmetric key algorithms require two keys in order to encrypt and decrypt a message. These are known as the public key and the private key. The public key can be given to anyone, while the private key must be kept secret.

The public and private key are connected mathematically with a one to one relationship; each public key has only one private key.

The public key can be derived from the private key, however the reverse is extremely hard and in practice would take multiple lifetimes.

Using the private key, one can sign a piece of data, creating a **digital signature**.

_The author understands that the low-level explanation is brief and short. Later versions may include more information._

