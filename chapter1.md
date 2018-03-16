# **Blockchain Foundation**

#### Overview of Cryptographic Hashing?

**High Level Explanation**

Imagine there was an alien machine, and the machine had a keyboard plus a screen. You type "hello" on the keyboard and immediately the screen displays "_2CF24DBA5FB0A30E26E83B2AC5B9E29E1B161E5C1FA7425E73043362938B9824_". You have no idea what that means. You delete the word and type "hello" again, and again the screen displays "2CF24DBA5FB0A30E26E83B2AC5B9E29E1B161E5C1FA7425E73043362938B9824". You realise that this machine is not talking to you, it's converting what you say into something else. This is why when you typed "hello", it displayed the same message again.

You then wonder, maybe there is a pattern in the way the words are generated. What if Instead of typing "hello", instead "Hello" was typed. The only thing that you changed was the lowercase h, to a capital 'H' and so the message that the machine outputs, should not be that different. The machine outputs "185F8DB32271FE25F561A6FC938B2E264306EC304EDA518007D1764826381969". There is no pattern at all. How is this machine converting the plain english into the gibberish?  
\_

After a year of typing in different messages, you notice three things:

* The message length was always 32 characters, no matter what was typed in.
* The message displayed gives no clue as to what was inputted. The only way to know what input generated that message, is to input the message itself and check. There are no shortcuts.
*  No message ever repeated. Whatever you typed in, a new message was displayed. Could there be a repeat of, but you never saw it? How long would it take to find this repeat? Is there a systematic way to find each repeat?

**Low Level Explanation**

You may have heard of SHA256 and MD5. These are what we call hashing algorithms. They define instructions on how to take an input which can be any size, and output a pseudo-random output of fixed length. The reason it is pseudo-random, is because with the same random input, we get the same random output.  
  
_A random algorithm would give a different output each time, even if you kept giving it the same input._

The output is always the same length, whether the input is larger or smaller than the output length.



The letter 'a' with SHA256 would hash to _'CA978112CA1BBDCAFAC231B39A23DC4DA786EFF8147C4E72B9807785AFEE48BB'_

The poem below would hash to "_5B595520A3E395D905C049CAC05B04517BC8D6BE76F5DBBA2FB3505BF337A42D_"  


> _It was easy enough  
> to bend them to my wish,  
> it was easy enough  
> to alter them with a touch,  
> but you  
> adrift on the great sea,  
> how shall I call you back?_
>
> _Cedar and white ash,  
> rock-cedar and sand plants  
> and tamarisk  
> red cedar and white cedar  
> and black cedar from the inmost forest,  
> fragrance upon fragrance  
> and all of my sea-magic is for nought._
>
> _It was easy enough—  
> a thought called them  
> from the sharp edges of the earth;  
> they prayed for a touch,  
> they cried for the sight of my face,  
> they entreated me  
> till in pity  
> I turned each to his own self._
>
> _Panther and panther,  
> then a black leopard  
> follows close—  
> black panther and red  
> and a great hound,  
> a god-like beast,  
> cut the sand in a clear ring  
> and shut me from the earth,  
> and cover the sea-sound  
> with their throats,  
> and the sea-roar with their own barks  
> and bellowing and snarls,  
> and the sea-stars  
> and the swirl of the sand,  
> and the rock-tamarisk  
> and the wind resonance—  
> but not your voice._
>
> _It is easy enough to call men  
> from the edges of the earth.  
> It is easy enough to summon them to my feet  
> with a thought—  
> it is beautiful to see the tall panther  
> and the sleek deer-hounds  
> circle in the dark._
>
> _It is easy enough  
> to make cedar and white ash fumes  
> into palaces  
> and to cover the sea-caves  
> with ivory and onyx._
>
> _But I would give up  
> rock-fringes of coral  
> and the inmost chamber  
> of my island palace  
> and my own gifts  
> and the whole region  
> of my power and magic  
> for your glance._



Since the input is unbounded and the output is bounded by some fixed length. There will be inevitably be different two inputs with the same output. This is called a collision. A hashing function can never be collision-free, due to the fixed output requirement. However, it can be collision resistant, meaning it is hard to find two inputs which give the same output.  
  
The question now arises, as to why must the output be fixed length. In order to answer this question, we should firs

