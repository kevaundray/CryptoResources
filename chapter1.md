# **Blockchain Foundation**

#### What is hashing?



**High Level Explanation**

Imagine there was an alien machine, and the machine had a keyboard plus a screen. You type "hello" on the keyboard and immediately the screen displays "_2CF24DBA5FB0A30E26E83B2AC5B9E29E1B161E5C1FA7425E73043362938B9824_". You have no idea what that means. You delete the word and type "hello" again, and again the screen displays "_2CF24DBA5FB0A30E26E83B2AC5B9E29E1B161E5C1FA7425E73043362938B9824". You realise that this machine is not talking to you, it's converting what you say into something else. This is why when you typed "hello", it displayed the same message again.  
  
You then wonder, maybe there is a pattern in the way the words are generated. What if Instead of typing "hello", instead "Hello" was typed. The only thing that you changed was the lowercase h, to a capital 'H' and so the message that the machine outputs, should not be that different. The machine outputs "185F8DB32271FE25F561A6FC938B2E264306EC304EDA518007D1764826381969". There is no pattern at all. How is this machine converting the plain english into the gibberish?   
_

After a year of typing in different messages, you notice two things. The message displayed gives no clue as to what was inputted. The only way to know what input generated that message, is to input the message itself and check. There are no shortcuts.  
The next thing you notice is that no message ever repeated. Whatever you typed in, a new message was displayed. Could there be a repeat of, but you never saw it? How long would it take to find this repeat? Is there a systematic way to find each repeat?

**Low Level Explanation**

Hashing is the process of mapping

