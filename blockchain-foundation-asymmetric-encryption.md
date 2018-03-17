# **Blockchain Foundation**

**Asymmetric Encryption**

**High level overview**

Imagine yourself in a room with a machine. You press a button on the machine and two keys with a box drop out of the back. After practicing with the keys and the box, you notice two things:

* Whenever you lock the box with key A, key A can no longer unlock it. You need key B to unlock it.
* Whenever you lock the box with key B, you need key A to unlock it.
* One key, B, has a lot more cuts than the other. It looks more complicated.

There is some connection between these two keys, you just don't know what it is. You tried to check the the cuts on the key to see if you could somehow go from one key to the other. No luck.

You press the machine again. This time only the keys come out. You try to lock the box with key C, and to your surprise it locks. You then try to open it with key A. No luck. You try key B, no luck. You try Key D and the box opens again.

You realise that whatever one key locks, only it's corresponding key can open. You start to think of the things you can do with this. If you give your friend one of the keys, then have him lock something with it, then only you will be able to unlock it. Which key do you give him?  You decide to give him the key with less cuts as this key looked like it was easier to make.

What if your friend copies the key? This means that you cannot send important information using your key, because if your friend copies the other key and misplaces it, then the person who found the key would be able to open the box. He may not tell you if this happens also. We have no choice, but to assume that the key you send your friend is known by everybody. We will call this the **public key. **The one that you did not send and are keeping to yourself will be known as the **private key.**

You start to think, if you are the only person to have your private key, then you could use this as to claim ownership of messages. Similar to putting your PIN into an ATM to get your funds. The bank assumes that no-one else has your PIN and so when your pin is entered along with your card into an ATM, the bank can verify that it was you.

No one has your private key and so when you lock a box with a message inside of it, everyone can verify that it was you who wrote the message by using the public key to open the box.

**Low Level Overview**

Asymmetric key algorithms require two keys in order to work. The public key and the private key. The public key can be given to anyone, while the private key must be kept secret.

The public and private key are connected mathematically with a one to one relationship; each public key has only one private key.



