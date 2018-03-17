# **Blockchain Foundation**

**Digital Signatures**

_Note: A high level overview was not given for digital signatures as this was included in the Asymmetric key - High level overview_

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





