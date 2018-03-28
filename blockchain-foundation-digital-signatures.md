# **Blockchain Foundation**

**Digital Signatures**

The author has not included a high level overview of what a digital signature is because it was covered in the _'Blockchain Foundation - Asymmetric encryption'_ Chapter.

**Low Level Overview**

A hand-written signature in the real world acts as _proof of identity_ for the signer and _proof of intent _towards what he is signing . In order for a person to verify your hand-written signature, they must see it. They could then copy it and use it in other places. This makes hand-written signatures vulnerable to forgery.

A digital signature is made using your private key and verified using your public key. This means that the verifier would never know how to copy your digital signature. This is because they do not need your private key to verify it. Your digital signature is also dynamic, meaning it changes for each document you sign. This means that someone cannot copy your digital signature from something you signed before, and use it for something you have never signed.

_How are digital signatures made?_

Let us assume that I created a pdf document and I would like to sign it, so that everyone who has access to my public key, can verify that it is my work in the pdf.

Naively, I would put the document into the asymmetric encryption algorithm with my private key and the output would be some cipher text.This cipher text would only be decipherable using the public key associated with my private key. I would then send the cipher text over to the receiver. He would use my public key to decipher and consume the content, knowing that I was the one who created it. There are a couple of problems with this method:

* Asymmetric encryption algorithms are slow to encrypt and decrypt. So the bigger the document, the longer it will take to encrypt and decrypt. _The reason as to why this is so, is beyond the scope of this book._
* If on tranmission over the internet, some of the file is corrupted then the receiver would have no way to know. When he attempts to decipher the cipher text, he will end up with a file that is not what the original sender intended.

An efficient way would be to:

1. Hash the original pdf document. This will output hashed text of fixed length. We will call this H.
2. Encrypt the hashed output with your private key. We will call this encrypted hashed text HP.
3. Send HP along with the pdf document to the receiver.

Upon receiving the file. The user will:

1. Decrypt the hash, HP. Resulting in H.
2. Hash the pdf received. We will call this hash, H' .
3. Check if H' = H.

If H' = H, then the original document was not tampered with upon transmission and the receiver can be sure that the sender is who they say they are. 

_Note that digital signatures are not used to secure the data, so that only the intended party can read it. This is what the public key is used for._

* _It is used to validate that the message was not changed upon transmission. **Data Integrity. **_
* _Since only the public key can decrypt, what the corresponding private key encrypt. When the sender decrypts the hash, he can be sure that it was only created by the sender who has that private key. **Message Authentication.**_
* _Since no-one else has access to the private key that signed the hash, we can be sure that if we receive a digital signature from a known party, then they cannot deny that they sent it. **Non-repudiation.**_

_Questions: _

* _If a malicious party was to intercept the pdf along the way and edit it, how would the receiver know that the file was edited? _
* _What if the hash function used, was not collision-resistant? How would this undermine data integrity, message authentication and non-repudiation?_





