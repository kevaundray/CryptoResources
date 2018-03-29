# Deep Dive : Proof Of Work

This chapter is being reviewed. Not suitable for consumption.

We will now formalise the concept to which we alluded to, when we stated that the miner needs to do some sort of '_work_' that will last on average 10 minutes.

The SHA256 hash of "_hello_" is:

> 2CF24DBA5FB0A30E26E83B2AC5B9E29E1B161E5C1FA7425E73043362938B9824

This output is in hex format and can be represented as a decimal number. The equivalent would be:

> 20329878786436204988385760252021328656300425018755239228739303522659023427620

This ouput can also be represented in binary:

> 101100111100100100110110111010010111111011000010

This can also be represented in words and characters, or ascii. The equivalent would be:  
![](/assets/Screen Shot 2018-03-20 at 12.33.23.png)

These are all different representations of the same output.

We will focus on the decimal representation.

In order to understand the probabilistic nature of proof of work. We will divulge into an example.

_Given two numbers, what is the probability of getting one of them?_

Answer: 50%

_Given three numbers what is the probability of getting one of them?_

Answer: 1/3 or 33%

_Given 10 numbers, what is the probability of getting 1 of them?_

Answer: 1/10 or 10%

_Given 10 numbers one to ten, what is the probability of getting a number below 5?_

There are four numbers below five. They are 1,2,3 and 4. The probability of getting either one of them is the combined probability of getting each one.

The answer can then be calculated by summing 1/10 + 1/10 + 1/10 + 1/10 = 4/10 or 40%.

The target in this situation was the number **5**.

What happens if we increase this target?

_Given 10 numbers one to ten, what is the probability of getting a number below **8**?_

The target in this situation is **8**.

There are seven numbers below 8. The probability of getting a number below 8, is therefore 7/10 or 70%.

**When the target increases the chances of finding a number below the target increases. The difficulty therefore decreases.  
When the target decreases, the probability of finding a number below the target decreases. The difficulty increases.**

_Why is this important in Bitcoin?_

Going back to our hashes above. We noted that the hash of a particular input could be written as a decimal representation.

The SHA256 hash of "hello**1**" is:

> 65997287284813763330462178930919765760826011093554635193003018840861226627243

The SHA256 hash of "hello**2**" is:

> 61135646788719019442779017887047393799578795125433597219691452054841458984676

The SHA256 hash of "hello**3**" is:

> 32528433039767960737972867567026659462191290014937929233691821910499380271760

The number that is appended onto the end of hello is known as the **nonce**.

_Why do we use the nonce?_

The nonce is used so that we can generate hash outputs, without changing the underlying data. Note, that hello1, hello2 and hello3 all convey the message _'hello'_.

If we set a target of 4 x 10^29. That is 4 with 29 zeroes after it. Then the SHA256 hash output of '_hello1'_ and '_hello2'_ would not be accepted.

The SHA256 hash of _'hello3'_ which gives an output of 3 x 10^29. Would be accepted, because it is below the target of 4 x 10^29.

If we increase the target, the probability of finding an output that is less than the target increases. Therefore, a hash will be found faster that is accepted. This is what we refer to as work. 

Bringing it to full circle:

Once the miner collects all of the transactions into a block, and all of the other relevant block variables. See '_Deep Dive: Blocks_' for further information.  
In the block header, there is a _nonce_ field, this number is incremented until when the whole block is hashed it gives a number less than the given target. This is sometimes referred to as **finding a block. **For clarity, we may refer to this as **Solving a block.**

_You mentioned that the nonce has a limit of 32 bytes, what happens when the nonce is exhausted and a number below the target is not found?_

One method is to increment the timestamp field, which will reset the nonce variable. The timestamp field is allowed to be incremented by up to two hours into the future.

Further details on how to circumvent the nonce will be covered in '_Deep Dive: Extra Nonce_'.

_How does this make sure that the miner solves the problem within 10 minutes?_

The bitcoin protocol checks every 2016 blocks, what the average time for solving the previous 2016 blocks were. If it was less than 10 minutes, then the target is decreased, making it more difficult to find a suitable hash output number. If the time was more than 10 minutes, then the target is increased, making it easier to find a suitable hash output number.

_Why 2016 blocks?_

If every block should take 10 minutes. Then 2016 blocks will take 2016 minutes.This is equivalent to two weeks .

_Why was two weeks chosen and not every block or every day?_

If we set it to every block, then every time someone **solves a block, ** the difficulty would change. Changing the difficulty too often.

If we set it to be one month, then the difficulty would take too long to change.

Two weeks seems like a happy medium.

_Note: There is a bug in the bitcoin protocol which calculates the difficulty of every block up to, but not including the 2016 block. The behaviour mentioned above was the intended. _

