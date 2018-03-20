# Deep Dive : Proof Of Work

We will now formalise the concept to which we alluded to, when we stated that the person who would like to be elected needs to do some sort of 'work' that will last 10 minutes.

When we hash an input.

For example the SHA256 hash of "hello" is:

> 2CF24DBA5FB0A30E26E83B2AC5B9E29E1B161E5C1FA7425E73043362938B9824

This output is in hex format and can be represented as a decimal number. The equivalent would be:

> 20329878786436204988385760252021328656300425018755239228739303522659023427620

This ouput can also be represented in binary:

> 101100111100100100110110111010010111111011000010

This can also be represented in words and characters, or ascii. The equivalent would be:  
![](/assets/Screen Shot 2018-03-20 at 12.33.23.png)

These are all different representations of the same output.

We will focus on the binary format and the decimal format.

In order to understand the probabilistic nature of proof of work. We will divulge into a simpler example.

_Given Two numbers, what is the probability of getting one of them?_

Answer: 50%

_Given three numbers what is the probability of getting one of them?_

Answer: 1/3 or 33%

_Given 10 numbers, what is the probability of getting 1 of them?_

Answer: 1/10 or 10%

_Given 10 numbers one to ten, what is the probability of getting a number below 5?_

There are four numbers below five. They are 1,2,3 and 4. The probability of getting either one of them is the combined probability of getting each one.

The answer can then be calculated by summing 1/10 + 1/10 + 1/10 + 1/10 = 4/10 or 40%.

The target in this situation was the number 5.

What happens if we increase this target?

_Given 10 numbers one to ten, what is the probability of getting a number below **8**?_

The target in this situation is 8.

There are seven numbers below 8. The probability of getting a number below 8, is therefore 7/10 or 70%.

**When the target increases the chances of finding a number below the target increases. The difficulty therefore decreases.  
If the target were to decrease, the probability of finding a number below the target decreases. The difficulty increases.**

_Why is this important in Bitcoin?_

Going back to our hashes above. We noted that the hash of a particular input could be written as a number.

The hash of "hello**1**" as a decimal would be:

> 65997287284813763330462178930919765760826011093554635193003018840861226627243

The hash of "hello**2**" as a decimal would be:

> 61135646788719019442779017887047393799578795125433597219691452054841458984676

The hash of "hello**3**" as a decimal would be:

> 32528433039767960737972867567026659462191290014937929233691821910499380271760

The number that is appended onto the end of hello is known as the \*\*nonce.

\*\*_Why do we use the nonce?_

The nonce is used so that we can generate hash outputs, without changing the data. Note, that hello1, hello2 and hello3 all have the original data untouched. The hello part.

If we set a target of 4 x 10 ^29. That is 4 with 29 zeroes after it. Then hello1 and hello2 would not be accepted.

hello3 which gives an output of 3 x 10^29. Would be accepted.

If we increase the target, the probability of finding an output that is less than the target increases. Therefore, the work will be done faster.

Bringing it to full circle:

Once the person who would like to be elected, collects all of the transactions into a block, and all of the other relevant block variables. See '_Deep Dive: Blocks_' for further information.  
In the block header, we see a nonce field, this number is incremented until when the whole block is hashed it gives a number less than the target.

_You mentioned that the nonce has a limit of 32 bytes, what happens when the nonce is exhausted and a number below the target is not found?_

This will be covered in '_Deep Dive: Extra Nonce_'

