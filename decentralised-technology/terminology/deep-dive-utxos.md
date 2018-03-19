# Deep Dive: UTXOs

Imagine a world in which there were no pennies and notes were exact chnage.

For example, you go to the supermarket and you want to buy a drink for $1. You have a $20 note. You give the cashier the $20 note and for your _change _ she gives you back a $19 note. You now have an unspent $19 note.

Another example, you go to the electronic store and you buy groceries. The groceries cost $24.90. You have a $35.85 note, which you give to the cashier. She gives you back as _change a_ $10.95 note. You now have an unspent $10.95 note.

A harder example. Let's say you go to the store to buy a game for $35. You have a $20 note, a $10 and a $6 note. Your \_unspent \_notes all come to $36. You give this to the cashier, and she gives you back a $1 note. You now have an unspent $1 note.

This is an important concept that Bitcoin uses. The important thing to note, is that no matter what your change is, you will always get a note back. The notes, just like money in the real world, are indivisible, you cannot rip a $20 note in half and have half the value, for example.

In Bitcoin transactions work in a similar manner. Relating back to the \_overview of Bitcoin, \_If Alice wants to send 5 Bitcoins to Bob, and in the past she has received 3 Bitcoins from Sally and 3 Bitcoin from James. Then  in order to send Bob 5 Bitcoins, she must send the 3 Bitcoin that she received from Sally and the 3 Bitcoins that she received from James. This means that she is sending a total of 6 Bitcoins. She only wants to send 5 to Bob, so what she will do in the Bitcoin software, is she will send the remaining Bitcoin to herself.

If that sounded confusing, then imagine that the cashier in the shop is the Bitcoin software and we are in the weird world we described above. Alice gives the cashier 6 Bitcoins with a note, because she only has two 3 Bitcoin notes, one she received from Sally and one She received from James. The note states that she wants to send 5 Bitcoins to Bob and she wants the change to go back to her. The cashier gives 5 Bitcoins to Bob, and gives Alice a 1 Bitcoin '_note'.  
  
_In order to test your understanding, we will go over some questions:  
  


