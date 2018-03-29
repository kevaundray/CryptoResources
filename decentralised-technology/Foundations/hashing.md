# **Blockchain Foundation**

#### Overview of Cryptographic Hashing

**High-Level Explanation**

Imagine finding an alien machine with a keyboard and a screen. You type `hello` on the keyboard, and immediately the screen displays `2CF24DBA5FB0A30E26E83B2AC5B9E29E1B161E5C1FA7425E73043362938B9824`. You have no idea what this means. You delete the word and type `hello` again, and again the screen displays `2CF24DBA5FB0A30E26E83B2AC5B9E29E1B161E5C1FA7425E73043362938B9824`. You realise that this machine is not talking to you but is converting what you type into something else. This is why every time you type `hello`, the machine displays the same message.

You wonder if there might be a pattern in the way the machine's responses are generated. You try typing `Hello`, with an uppercase `H`, instead of  `hello`, with a lowercase `h`. You predict that the response will be the same, but the machine outputs something different: `185F8DB32271FE25F561A6FC938B2E264306EC304EDA518007D1764826381969`. You're starting to think there is no pattern at all. How is this machine converting plain English into gibberish?

After spending a long time typing in different messages, you notice three things:

* The response length is always 32 characters, no matter what you enter.
* The response provides no clues about the input. The only way to know what input generates what response is to enter the input and check the result. There are no shortcuts.
* No response is ever repeated. Every time you enter a new input, a new response is displayed. Could there be duplicate responses you didn't notice? How long would it take to find a duplicate? Is there a systematic way to find duplicates?

**Low-Level Explanation**

You may have heard of SHA256 or MD5. These are called __cryptographic hash functions__. Cryptographic hash functions define instructions for taking an input of any size and generating a pseudorandom output of fixed length (this means the output is always the same length, regardless of the size of the input).

Note: Cryptographic hash functions are described as __pseudorandom__ because the same input generates the same output (as in the `hello` example above); a __random__ algorithm would give a different output each time, even if you kept using the same input.

For example, inputting the letter `a` into the SHA256 cryptographic hash function generates `CA978112CA1BBDCAFAC231B39A23DC4DA786EFF8147C4E72B9807785AFEE48BB`.

The poem below hashes to `5B595520A3E395D905C049CAC05B04517BC8D6BE76F5DBBA2FB3505BF337A42D`.

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

Because the input is unbounded (meaning it can be any length) and the output is bounded by a fixed length, there will always be cases where two different inputs generate the same output. This is called a __collision__. It is impossible for a cryptographic hash function to be collision-free due to the fixed output requirement. However, cryptographic hash functions _can_ be __collision-resistant__, meaning it is very difficult to find two inputs that generate the same output.

You may be wondering why the output of a cryptographic hash function has to have a fixed length. Think back to the alien machine and the impossibility of gathering any information about the input from the output. If the output varied along with the input, the function would be leaking information about the input and would therefore not be secure.

For example, imagine a function where inputting `hi` outputs `1A3D451W`, and inputting `g` outputs `2D4G`. In this case, halving the length of the input also halves the length of the output. A hacker can use this information to make it easier to guess the corresponding input of an output by limiting the number of possible solutions to check, making the function less secure.

To try out a cryptographic hash function yourself (in this case, SHA256), click [here](https://www.movable-type.co.uk/scripts/sha256.html). You'll notice that if you try the same inputs as in our alien machine example above, you'll also receive the same outputs.
