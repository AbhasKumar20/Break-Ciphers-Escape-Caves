# Analysis 
Key Observations to conclude that this was a  Play Fair cipher.

1. THE HINT: At the onset of the chamber(for level 2) after giving the command "go" and paying respect to The spirit of Cave Man, he utters "You have been blessed, my child. Keep in mind that you must always believe in yourself and PLAY FAIR".
So the use of "PLAY FAIR" gave us the hint that this might be the famous Playfair cipher cryptosystem.

2. THE CODE: And to work with the Playfair cipher we required a key, then we focused on the sequence made up of characters  '. ' ,  '  '  and '-'. We figured out that these correspond to something called "Morse Code". We figured out mapping and came to know that it is written "SECURITY". So we came to the conclusion that this must the required key of the Playfair cryptosystem that we were speculating. 

3. An aspect of Playfair ciphers that separates it from simple substitution ciphers is the fact that it will never contain double-letter digrams, like "LL". If there are no double letter digrams in the ciphertext and the length of the message is long enough to make this statistically significant, it is very likely that the method of encryption is Playfair. Since given cipher was in accordance with this fact too. We concluded that this has to be a Playfair cipher cryptosystem.

# Decryption algorithm  

We used Playfair cipher Decryption Technique to decrypt the Ciphertext. In this Decryption Technique, we decrypted a pair of alphabets (digrams) instead of a single alphabet. Our Decryption Technique mainly consists of 4 steps:

Step 1. Finding the Key: We figured out that the given string  "... . -.-. ..- .-. .. - -.--" is a Morse code, then by using standard notations we converted the Morse code into the key as-
[...]=S [.]=E [-.-.]=Q [..-]=U [.-.]=I [..]=R [-]=T [-.--]=Y.
Hence "... . -.-. ..- .-. .. - -.--"= "SECURITY".

Step 2. Construction of 5×5 Grid:  A 5×5 grid of alphabets with key "SECURITY" was constructed by filling in the letters of the keyword (minus duplicates) from left to right and from top to bottom, and then filling in the remainder of the matrix with the remaining letters in alphabetic order.
                     [  [S,E,C,U,R],
                       [I,T,Y,A,B],
                       [D,F,G,H,K],
                       [L,M,N,O,P],
                       [Q,V,W,X,Z]  ]

Step 3. Decrypt the Digrams: First, all the whitespaces together with punctuations were removed .followed by splitting the ciphertext into pairs of two letters (digrams). Now we applied standard rules given below to decrypt the cipher-
	A. If both the letters are in the same column: Take the letter above each one (going back to the bottom if at the top).
	B. If both the letters are in the same row: Take the letter to the left of each one (going back to the rightmost if at the leftmost position).
	C. If neither of the above rules is true: Form a rectangle with the two letters and take the letters on the horizontal opposite corner of the rectangle.

Obtained Plain text after 3 steps:
	
BE WARY OF THE NEXT CHAMBER, THERE IS VERY LITTLE IOY THERE. SPEAK OUT X THE PASSWORD "OPEN_SESAME" TO GO THROUGH. MAY X YOU HAVE THE STRENGTH FOR THE NEXT CHAMBER. TO FIND THE EXIT YOU FIRST WILXL NEXED TO UTTER MAGIC WORDS THERE.

Step 4: Then we removed 'X' between the repeating letters as during the encryption, repeating plaintext letters that are in the same pair must have been separated with a filler letter('X'). Also, we noticed that word "IOY" doesn't make sense, so we replaced "I" with "J" to get "JOY" as in PLAY FAIR ciphers, the letters 'I' and 'J' count as one letter and selection is choice dependent.

So final Plain text obtained is:

BE WARY OF THE NEXT CHAMBER, THERE IS VERY LITTLE JOY THERE. SPEAK OUT THE PASSWORD "OPEN_SESAME" TO GO THROUGH. MAY YOU HAVE THE STRENGTH FOR THE NEXT CHAMBER. TO FIND THE EXIT YOU FIRST WILL NEED TO UTTER MAGIC WORDS THERE.