# **Blockchain Foundation**

#### Checksum

**High-Level Explanation**

Imagine you bought a laptop from Amazon. You input your address and pay for item using your credit card. When the item arrives at your door, you notice that the packaging is damaged. Because of this you return the package and you get a replacement. In this scenario, you did not bother to open the package because if the package has been damaged, then it is likely that the product inside is also damaged. You and the e-commerce website implicitly agreed that the package would arrive in good condition. If you and the e-commerce site had agreed that the packaging would be damaged, then you would not have returned it, right? The condition of the package is being used to verify the products integrity, ie whether it has been damaged or not. If the package is damaged, the product inside is probably damaged and so we should not accept it.

**Low-Level Explanation**

The checksum is a piece of data that can be used to verify whether the information received has been tampered with or has errors.

A simple checksum algorithm would be to check the data before submission and for every vowel, we add one.

For example, If we wanted to send the word '**abc**'. It has one vowel in the word, the letter 'a'.  Therefore our checksum would be 1. We would then send the data and the checksum to the receiver with the checksum appended to the end 'abc1'. Upon receiving, he would take the data 'abc' and calculate the checksum by counting the number of vowels. If this matches the checksum that they received appended to the data, then the chances of there being an error or the data being tampered is _reduced_. _Why is this checksum not secure? What does it not account for?_

This checksum does not account for consonants. If the letter 'b' was lost in transmission, then the checksum would still be 1. The receiver would still have calculated the correct checksum. The problem is that this checksum is not a good indicator of lost data. A good checksum will output a significantly different value, even for small changes to the data.

Tyin_g back to the high-level overview analogy, the checksum can be seen as the packaging for the data._

Concluding this section, we see that checksums are used to check for errors and possible corruption of data. This chapter does not include many examples of checksum as the conceptual understanding of what it is, is the objective.

