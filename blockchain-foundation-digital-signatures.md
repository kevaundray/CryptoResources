# **Blockchain Foundation**

**Digital Signatures**

_The author has not included a high level overview of what a digital signature is because it was covered in the 'Blockchain Foundation - Asymmetric encryption' _Chapter.

**Low Level Overview**

A signature in the real world acts as a proof of identity for the signee. In order for a person to verify your signature, they must see it. They could then copy it and use it in other places. This makes hand-written signatures vulnerable to forgery.

A digital signature is made using your private key and verified using your public key. This means that the verifier would never know how to copy your digital signature. Your digital signature is also dynamic, meaning it changes for each document you sign. This means that someone cannot copy your digital signature from something you signed before.

_How are digital signatures made?_

Let us assume that I created a pdf document and I would like to sign it, so that everyone who has access to my public key, can verify that it is my work in the pdf.

Naively, I would put the document into the encryption algorithm with my private key and the output would be some cipher text, that would only be decipherable using the public key associated with my private key. I would send the document over, however there are a couple of problems with this method:

* Asymmetric encryption algorithms are slow to encrypt and decrypt. So the bigger the document, the longer it will take to encrypt and decrypt
* If on tranmission over the internet, some of the file is corrupted then the receiver would have no way to know.

An efficient way would be to:

1. Hash the pdf document. This will output a hashed text of fixed length. We will call this H.
2. Encrypt the hashed output with your private key. We will call this ecnrypted hashed text HP.
3. Send HP along with the pdf document to the receiver.

Upon receiving the file. The user will:

1. Decrypt the hash, HP. Resulting in H.
2. Hash the pdf received. We will call this hash, H prime.
3. Check if H Prime = H.

If H Prime = H, this means that the original document was not tampered with upon transmission and the receiver can be sure that the sender is who they say they are.

_Question: If a malicious party was to intercept the pdf along the way and edit it, how would the receiver know that the file was edited? _

