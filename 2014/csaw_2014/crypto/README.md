## Crypto 200

If you know the basics about cryptography, it's going to be easy.

When you `nc 54.209.5.48 12345`, they will give you a intro message ant the encrypted text that begins after the word "psifer text:".

In order to decrypt it automatically, you may have to use ciphers to decrypt it, or programme a code which can guess answers.
Since the alphabets constantly changes with a specific length, you may realize that this encryption is a "ceaser cipher" or a "ROT-13 algorithm"

Anyways, While you are on a wild test, you will realize that the answer starts with the word "the answer to this stage is".
by using this keyword (the answer to this stage is),  you can create an automation script if you use rot-13 algorithm to solve challenges.

The second stage was quite interesting - characters seem to be positioned in a wrong way.
since the positions of strings are changing without the actual change of length, you will later find out this one uses a transposition cipher.

However, there was a some sort of problem - there was a shift of strings depending on the columns while making an automation script.
Since it was too difficult to code it with PHP, I just decided to do this one manually and guess password for this stage.

The third one has a long set of strings containing a whole blocks of strings with 5 capital alphabets. 
By thinking/googling for this algorithm, you will find out that this one is made by Viegnere cipher.

If you know this cipher, you will realize that you need to guess out the keys. 
but no one could be able to bruteforce if you have a long sets of keys!!!

so by using few online tools from google, you will find out the length of the key (`http://www.simonsingh.net/The_Black_Chamber/vigenere_cracking_tool.html`) - finding length of key is described on the internet, you should check on it.

after you find the length of the key, you will have to decrypt both the keys and the string. In order to do so, you have to google out the "dictionary bruteforcing vigenere solver". After you get sets of keys from several trials of third stage, you can create a automation script and solve the challenge.


```
root@stypr:/home/stypr/www/~local# php flag.php
Congratulations, you have solved stage 3. The flag is: flag{IGraduatedPsiferSchoolAndAllIGotWasThisLousyFlag}.
```