# Defcon-Shoot-26-Puzzle
![lanyard image](https://pbs.twimg.com/media/DkLqeIsUYAE46Lm.jpg "lanyard")

Here's a writeup of the defcon shoot 26 puzzle. The badge this year was a "banana clip" which was a sand pmag dyed yellow, scented using banana scent. Also included were "banana" stickers, a mag pull to attach a lanyard to, and extra sarcastic stickers and LEDs (not pictured). 

## Step 1
Starting with the lanyard it is obvious there's some ciphertext. There are two distinct sections, designated by "|". I wanted to start off easy to get people into the contest so this is just ROT13 that decodes to:
hint for step two not the first

## Step 2
The second section of the lanyard ciphertext moved to the Vigenère cipher. I left some spaces in there to help. There's not enough ciphertext to do much analysis, but I tried to make the hint as obvious as I could in the limited text I had available.

Interestingly multiple people mentioned they tried the key "second" which resulted in: 
GVWLIRCAVGLO HEUHREBU IZGZDEXN
secondsecond secondse condseco
oruxvokwtsyl pastebjq gltwlavz
Notice the "pastebjq" which is very close to pastebin. The reason this happened is the actual key length was 9 characters and not 6. So while "second" is part of the key, and it aligns with those 6 characters, the rest of the clear text is incorrect because the wrong key is used for those characters. The correct key is "thesecond" which results in:
GVWLIRCAVGLO HEUHREBU IZGZDEXN
thesecondthe secondth esecondt
nosteponsnek pastebin ehcxpruu
By going to [this pastebin link](https://pastebin.com/ehcxpruu) it gets you to step 3

## [Step 3](https://pastebin.com/ehcxpruu)
This step was the most work for me, I wrote some code in the [esoteric language "chicken"](https://esolangs.org/wiki/Chicken#Examples) which each operation is designated by the number of "chickens" on a line. Normally this wouldn't be hard to write a simple program that outputs some text, but you can take [at the whitepaper](https://isotropic.org/papers/chicken.pdf) or a [presentation](https://youtu.be/yL_-1d9OSdk?t=37) to see how much help that was. 

Anyway after successfully writing the chicken script, I wanted to make it slightly harder so I translated it to norwegian (kylling). If you figured this part out, this step was easy as there is [an online interpreter](http://torso.me/chicken) you just had to paste the chickens into, and you got to the next [pastebin link.](https://pastebin.com/z8W4WDCC)

## [Step 4](https://pastebin.com/z8W4WDCC)
Next up I wanted to use a language that didn't have an interpreter online, and most of the languages listed on that esoteric wiki page were derivatives of brainfuck. [Drive-in window](https://esolangs.org/wiki/Drive-In_Window) seemed interesting so I went with that. 

Unfortunately I reversed the last two characters, but after someone told me they had trouble I double checked and corrected it. Also one of the characters decoded to "8" while the others decoded to ascii values. This "8" meant the literal "8" character, not the ascii backspace character, but I also adjusted that to the ascii value for 8 to clear things up. 
I tweeted this correction, @boombadge retweeted it, and I posted it on slack, so hopefully if you were working on this you saw exactly when this page was updated. If anything it held up the people in the lead and let others catch up.

This drive-in window script decoded to [this link](https://pastebin.com/YvPi8QUw)

## [Step 5](https://pastebin.com/YvPi8QUw)
I liked the idea of [Illegal Numbers](https://en.wikipedia.org/wiki/Illegal_number), and wanted to use them as a way to decode the next pastebin link. So for this step you needed to find the HDCP key, TI signing key, ps3 dongle key (there were multiple but I think I used the most distributed one), and AACS key. 

Similar to previous steps I just used the portions of the key that decoded to the next pastebin link.

## [Step 6](https://pastebin.com/JQwNUJfG)
Almost there, this is the last pastebin link. You had to find the answer to "What is the criteria used to design DES s-boxes?". The story of DES s-Boxes was always very interesting to me. S-boxes are used as lookup tables for one step in DES that permutes the plaintext. The NSA worked with IBM on the algorithm, then changed the S-box values. Everyone was immediately very suspicious suspecting a trapdoor was added, and IBM and the NSA wouldn't explain how the values were determined. This is why [nothing up my sleeve numbers](https://en.wikipedia.org/wiki/Nothing_up_my_sleeve_number) are often used when possible for cryptographic constants.

Around a decade later [differential cryptoanalysis](https://en.wikipedia.org/wiki/Differential_cryptanalysis#History) was rediscovered and written about publically. DES's s-boxes had the best possible design to protect against this kind of attack. Then IBM and the NSA came out and said "oh yeah we already knew about this a decade ago, which is why we designed the s-boxes that way"

Back to the question of: "What is the criteria used to design DES s-boxes?", I was looking for "strict avalanche criteria". I was hoping this would be somewhat easy by using the word "criteria", and by tweeting @boombadge it let everyone verify when someone solved the last step. It took the winner a few attempts more than I expected after reading [some](http://citeseerx.ist.psu.edu/viewdoc/download?doi=10.1.1.193.2902&rep=rep1&type=pdf) [papers](https://link.springer.com/content/pdf/10.1007%2F3-540-39799-X_41.pdf)

![80per](https://pbs.twimg.com/media/Djuq2AmUUAAC-5i.jpg "80per")
The winner of the 80% AR15 lower was [@gigstaggart](https://twitter.com/gigstaggart). A serial number isn't required on an 80% lower, but matt added an SQL injection for fun. He also had some fun with the safe, semi, full selector markings.
