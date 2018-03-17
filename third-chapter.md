# **Blockchain Foundation**

#### Merkle Roots and Tress

**High Level Explanation**

For arguments purpose, I will assume that if you are reading this, you are one alive and two you had parents.  Now what if instead of your mum marrying your dad, she married Fred. You would not exist. Your mum and your dad, are the only combination of people who could have conceived you. If either your mum or your dad was not in the equation, then you would not exist. Let's take this further, what if your grandma decided to not marry your grand father. Your mum would not exist, and subsequently you would not exist. You can imagine the tree, would look like the below image:

![](/assets/Tree.png)

Notice Oliver at the top? If any one of the below family members change, then he will change or cease to exist.

We will call the guy at the very top, the **family root. **He is the glue that connects every single other member together. We will call the other members **family leaves** and the structure you see above will be called a **family tree**.

One day a really old lady walks up to Oliver and says "I am a part of your family tree. My name is Brenda, I had a daughter called Ingred". How would Oliver verify this? Efficiently? Without going through every family member?

In order for Oliver to Verify, he must go to Martin and ask Martin, to give him the details of his parents. Martin gives Oliver the names 'Ingred' and 'James'. Oliver now asks Ingred, to give him all of the details on her mother. Ingred gives her the name 'Brenda' and after checking her birth certificate and passport, we verify that she is indeed related to Oliver.

The week after, an old man walks up to oliver and says " I am a part of your family tree, My name is Gary and we had a child called 'Laura'. Now Oliver knows that Laura is on the right hand side of the tree and so he asks Niacole for the details on her parents. Nicole gives Oliver the names 'Kyle' and 'Lisa'. The old man said they had a child called 'Laura' though. So something is amiss. Oliver asks Lisa for her parents details and she gives Oliver the names 'Graham' and 'Hope'. Oliver can be certain that Gary is not a part of his family tree, and was in fact an imposter.

Did you notice that in the first scenario, in order to verify Brenda was a part of his family tree, he did not bother going down Nicoles family tree because her family line was not the one in question. Immediately, the amount of family members that Oliver needs to find is halved.

After asking Martin for his parents, he knows he only needs to check Ingreds family tree and so the amount of family members that he needs to find is halved again.

Oliver only needed partial parts of his family tree in order to verify that someone was a family member.



**Low Level Explanation**

On your computer, you have a 100GB file. You decide to split it into four 25GB files and send them to four friends so that you can free up space on your laptop. When you ask for the files back, how can you be certain that your friends did not edit one of the files? What if you only needed one out of the four files back, is there a way to validate that one file without getting the other three files? Remember you no longer have a the 100GB file with you, it's takes up too much space.  
  
In order to do it, we will form a merkle tree. To do this we must first hash all four files. Like so:  
  
![](/assets/filetohash.png)



We will now send all four files to our friends, so that we no longer have F1... F4, just their hashes which are significantly lower in storage space, due to their fixed length output.  
  
We now pair up each hash, concatenate them  and hash the result. I.e Hash\(H1+H2\) 

_Note: H1H2  refers to concatenating H1 and H2 then taking their hash. Hash\(H1H2\)._



![](/assets/Group.png)



The final step would be to hash the two hashes H1H2 and H3H4.

![](/assets/Group2.png)



The top hash is called the **merkle root**. The bottom hashes are called the **merkle leaves** and everything in between is called a **merkle nodes**.

Notice that if any of the merkle leaves or nodes change, then the merkle root changes.

