# AESProject
Applying AES in C#


Brief Outline:
	To start off I first did the s box implementation. I use the sbox array as a lookup table for the text that is input into the array (hardcoded) and pass the text into my substitution function. Which then reference the sbox to return values. Next was row shifting, instead of bitwise shifting I decided to go with a circular shift instead. I call on my rowShift function and me for loop to make substitutions into a 2-dimensional matrix. The text gets put in vertically, but the actual substitution happens horizontally. The first row is not touched by the row shift, the second-row shift to the left once, the third row flips the first two entries with the second two entries, and the fourth-row shift once to the right. Next was my mix columns implementation to do this I made my function (galoisMultiplication) take column of 4 bytes and performed the multiplication. Also, my mixColumn function takes in the 4 bytes of text and saves them into the array to be multiplied by the galoisMultiplication function. Lastly, was the round key I take the 16 bytes that was entered into the card and XOR them to the expanded key. When the roundKey function is called it switches the bytes that are used by using the first 16 bytes of the expanded key first and then using the next 16 bytes to be XOR’d against. I have the memcpy in them to move the bytes that are being used. After all of this is implemented, I use my main function to call on everything to achieve an AES encryption and output the main message to the screen, my key, and the new encrypted message. I did not have time to implement decryption here sadly because I have 3 projects I need to finish up in other classes. 

The main difficulty with this was the mix columns when I tried to implement in python instead of C++, using the unsigned() in c++ helps so much with implementing something like this because it took a lot of the conversions out of the equation. One other issue I delt with was converting the hexadecimal back to text so I just kept it in hex. I feel like this truly did help me understand AES fully. I watch a lot of YouTube videos on how to calculate and move around the mixColumns part that helped. All the other parts of the Implementation were not that bad. I believe that implementing this will help me in future endeavors, because I can honestly say I have not done a project like this one before and it made me enjoy cryptography a lot more. I think cryptography is a unique thing and needed. Implementing AES showed me how truly remarkable encryption can really be and how the security of messages and encrypting messages is a very important thing. 
