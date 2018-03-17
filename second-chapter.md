# **Blockchain Foundation**

#### Checksum

**High Level Explanation**

Imagine you bought a laptop from an online e-commerce store. You input your address and pay for item using your credit card. When the item arrives at your door, you notice that the packaging is damaged. Because of this you return the package and you get a replacement. In this scenario, you did not bother to open the package because if the package has been damaged, then it is likely that the product inside is also damaged. You and the e-commerce website implicitly agreed that the package would arrive in good condition. If you and the e-commerce site had agreed that the packaging would be damaged, then you would not have returned it, right? The condition of the package is being used to verify the products integrity, ie whether it has been damaged or not. If the package is damaged, the product is probably damaged and so we should not accept it.  
  
**Low Level Explanation**

 The checksum is a piece of data that can be used to verify whether the information received has been tampered with or has errors.  
  
A simple checksum algorithm would check the data before submission and for every vowel, we add one.  
  
If we wanted to send the word 'abc' because it has one vowel in the word, the letter 'a', our checksum would be 1. We would therefore send the data and the checksum to the receiver as follows 'abc1'. Upon receiving the receiver would take the data 'abc' and calculate the checksum by counting the number of vowels. If this matches the checksum that they received along with the data, then the chances of their being an error or the data being tampered is reduced.   
  
What if when we sent the data, the letter 'b' was lost on transmission? The checksum would still be correct, as it does not account for consonants. A good checksum will output a significantly different value, even for small changes to the data.  
  
Concluding this section, we see that checksums are used to check for errors and possible corruption of data. This chapter does not include many examples of checksum as the conceptual understanding of what it is, is the objective.  
  


