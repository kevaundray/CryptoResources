# **Blockchain Foundation**

#### Merkle Roots and Tress

**High-Level Explanation**

If you are reading this sentence, you are one alive and two you had or have parents.  Now imagine that instead of your Mum marrying your Dad, she married Fred. You would not exist. Your Mum and your Dad, are the only combination of people who could have conceived you. Therefore, If either your mum or your dad did not exist, then you would not exist. Let's take this further, what if your grandma decided to not marry your grand father. Your mum would not exist, and subsequently you would not exist. You only exist because of the unique combinations of ancestors. You can imagine the tree like structure, would look like the below image:

![](/assets/Tree.png)

Notice **O**liver at the top? If any one of the below family members change, then he will change or cease to exist.

We will call the guy at the very top, the **family root. **He is the glue that connects every single other member together. We will call the other members **family leaves** and the structure you see above will be called a **family tree**.

One day a really old lady walks up to **O**liver and says "I am a part of your family tree. My name is **B**renda, I had a daughter called **I**ngred". _How would Oliver verify this? Efficiently? Does he need to ask every family member?_

In order for **O**liver to Verify, he must ask **M**artin to give him the details of his parents. Martin gives Oliver the names '**I**ngred' and '**J**ames'. **O**liver now asks **I**ngred, to give him all of the details on her mother. Ingred gives her the name '**B**renda' and after checking her birth certificate and passport, we verify that she is indeed related to **O**liver.

The week after, an old man walks up to **O**liver and says " I am a part of your family tree, My name is **G**ary and we had a child called '**L**aura'. Now Oliver knows that **L**aura is on the right hand side of the tree and so he asks **N**icole for the details on her parents. **N**icole gives **O**liver the names '**K**yle' and '**L**isa'. The old man said they had a child called '**L**aura' though. So something is amiss. **O**liver asks **L**isa for her parents details and she gives **O**liver the names '**G**raham' and '**H**ope'. **O**liver can be certain that **G**ary is not a part of his family tree, and was in fact an imposter.

Did you notice that in the first scenario, in order to verify **B**renda was a part of **O**liver's family tree, he did not bother going down **N**icoles family tree because her family line was not the one in question. Immediately, the amount of family members that **O**liver needs to find is halved.

After asking **M**artin for his parents, he knows he only needs to check **I**ngred's family tree and so the amount of family members that he needs to search through is halved again.

**O**liver only needed partial parts of his family tree in order to verify that someone was a family member and indeed related to him.

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

The top hash is called the **merkle root**. The bottom hashes are called the **merkle leaves** and everything in between is called a **merkle nodes or merkle branches**.

Notice that if any of the merkle leaves or nodes change, then the merkle root changes.

Saving this tree diagram onto your computer, we can now use this to check if a friend sends you an altered file, without the other three files.

Scenario one:

Your friend James, sends you file number two, F2. You now want to check using your merkle tree, whether the file has been altered.

You take the file number two and then hash it, to get H'\(2\). You then take the known H\(1\) from Storage, and do H1H'2.

If H1H'2  equals H1H2 then the file has not been altered.

Now what If I only wanted to store the merkle root and still be able to verify the transactions?

Again we would take the file F2, and hash it to get H'2. We would then ask friend one for the H1, not the file itself, the Hash of the file.

Then ask friend 3 and 4 to hash the files themselves and send me H3H4.

Now, we now have H1,H'2, and H3H4. The only thing we know to be true, is the merkle root.

In order to verify that H'2 is valid, we must first derive H1H'2. Using this we can then derive H1H'2H3H4.

If H1H'2H3H4 equals our merkle root H1H2H3H4, then F2 was indeed not altered.

