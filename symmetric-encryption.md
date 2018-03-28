# **Blockchain Foundation**

**Symmetric Encryption**

**High-Level Explanation**

Imagine yourself in a room with a box. You have one key and this key like a real key, opens and closes the box. If you want to hide anything in the box from someone else, you must ensure that they do not have a copy of the key.

**Low level overview**

Encrypting is the process of converting a plain message into a secret message. The process of encryption is used to hide the original message from third parties.

Decrypting is the process of converting a secret message back into the plain message.

Using a symmetric key algorithm, you must supply a **key, ** along with the plain-text that you wish to encrypt. The algorithm, then outputs the corresponding _cypher_ or _encrypted text_.

In order to decrypt the _cypher text_, the receiver will use the **same key.**

One example of a symmetric key algorithm, is that of a letter shift.

The algorithm states that:

* Given the plain text and a key, **k**,  between 0 and 26.
* Take each letter in the plain-text and shift it along the alphabet, **k times.**

If the key is **1**, the letter **'a'** when encrypted becomes '**b**'.

If the key is **2**, the letter '**a'** becomes **'c'.**

if the key is **3**, the letter **'d'** becomes **'g'.**

The sentence **'hello'** with a key of **2** becomes **'jgnnq'**. In order to decrypt this, the receiver would use the **same key ** to reverse the process.

A well known symmetric key algorithm is _AES_. You can try it here: [https://aesencryption.net/](https://aesencryption.net/)

