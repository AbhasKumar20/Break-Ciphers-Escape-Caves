Steps followed to crack the Ciphertext:

1. Began with Frequency analysis of the ciphertext given in the game. We used python code(attached in Q.5.) to analyze the frequency of characters in the C.T.
In this analysis, we found that the total length of C.T. was 324 characters, and the frequency of all characters present in the C.T.
By checking these frequencies against the average frequency of alphabets in the English language(discussed in the second lecture), one can say that since 'y' character had the highest frequency in C.T., hence it could be mapped to character 'e' in P.T. Next frequent alphabet in C.T. 'm' was mapped to 't'(the second most frequent character in English). Other than these two characters, the average frequency of character occurrence in the English language was not of much help since the C.T. was of small length.  

2. Since frequency analysis of characters could not help, we moved to the next step that was looking for the reoccurrence of words.
We found "iepjoys" occurring twice but with spaces in different positions. {"ie pjo ys", "iepjo ys"}. This gave the gist that spaces are misplaced in the P.T. This increased the difficulty level of decryption s.t. spaces have no relevance in the P.T.
Next, we observed "TeE" ("T", "E" were replaced in step 1) was occurring 8 times in the C.T. and converting it to "THE" seems most sensible. so "e" -> "h"
Next we find an occurrence of "EE" in P.T. which could make a word like "see",  "bee",  "free", "tree". Since "a" is the prefix of "EE" and "a" is amongst most frequent letter in C.T., it seems right to map to a more frequent letter like "s", rather than "r" or "b" and experiment with making it "see", thus mapping "a"->"s"
next, "whTEsEST" was found twice and it clearly looks like it could be the word "Interest" hence w->i, h->n, s->r.
Next "INTE RE STIN r" could only mean "interesting", hence "r" is mapped to "g" in P.T.
"THpNTHIS" looks like "Than This" so "p"->"a"
"INTE RE STIN GTHANTHISgN E!" looks like "INTERESTING THAN THIS ONE" so "g"->"o"
"THI SjES SAG EISA" looks like "THIS MESSAGE IS A", so "j"->"m"
"THE REI SNOT HINGO tI NTEREST" looks like "THERE IS NOTHING OF INTEREST", so t->f
"iAbES" can be "CAVES" or "GAMES" (contextually). We will try mapping it to "CAVES" (since mapping it to "GAMES" was a fail), map i->c, b->v.
Since we were talking about chambers in the game "CH AMo EROFT HECAVES" will be "CHAMBER OF THE CAVES", so map o->b
"k ATER" will be "LATER", so map k->l
"vI LL" will be "WILL", so map v->w
Since we have been working on simple substitution cipher, "SIMfLES nB S TITnTI ONCIfHER" can be "SIMPLE SUBSTITUTION CIPHER", map f->p, n->u
"SH IFTE uBx8 PLACES" looks like "SHIFTED BY 8 PLACES", so x->y, u->d
"dUOTES" is "QUOTES", so map d->q
Finally, we have all the characters decrypted and makes sense.

3. To Crack digits:

Since our decryption technique didn't consider the digits which can also be encrypted like alphabets, we were required to figure out the mapping for digits as well( since the  password "TYRGU03DIQQ" contained digits 0 and 3). If d_1 and d_2  were the two digits mapped to 0 and 3 respectively after encryption  then we must have (d_1+s)mod10=0 and (d_2+s)mod10=0 such that |d_1-d_2|=3 and d_2>d_1 where s is the numbers of digit shifted( which may not be 8 as mentioned in the plain text obtained so far). Possible pairs for (d_1,d_2) following the required constraints are (1,4),(2,5),(3,6),(4,7),(5,8) and (6,9). Only pair (6,9) with s=4 satisfies both equation. So actually digits were by 4 places and (0,3) mapped to (6,9).

Q4 Mapping
10 Points
What is the plaintext space and ciphertext space? What is the mapping between the elements of plaintext space and the elements of ciphertext space? (Explain in less than 100 words)

Cipher text space:   [a-z]-\{c,l,q,z\}U\{0,3,8\}U\{ ,!,.\}U\{P,A,S,N,M\}

"wsam ie pjo ysgtm eyipbya .P axg niphay y, mey syw ahgm ewhrg tw hmysyam wh meyiepjo ys .Ag jygtmeyk pmys ie pjo ysavw kkoyjgsy whmy sy amwh rmephmewagh y!Me yigu ynay utg mew ajya apr ywap awjfkya no a mwmnmw ghiwfeyswhve wieuwr wm aepby oyyhae wtmy uox8 fkpiya.Me y fpaavgs uwa mxSrN03u wd dvwmegnmmey dngmya. Mew awameyt"

Plain text space:[A-Z]-\{J,K,X,Z\}U\{4,6,9\}U\{ ,!,.\}
"IRST CH AMB EROFT HECAVES .A SYO UCANSE E, THE REI SNOT HINGO FI NTEREST IN THECHAMB ER .SO MEOFTHEL ATER CH AMB ERSWI LLBEMORE INTE RE STIN GTHANTHISON E!TH ECOD EUSE DFO THI SMES SAG EISA SIMPLES UB S TITUTI ONCIPHERINWH ICHDIG IT SHAVE BEENSH IFTE DBY4 PLACES. TH E PASSWOR DIS TYRGU69D IQ QWITHOUTTHE QUOTES. THI SISTHEF"

Let D be the mapping of ciphertext character to plaintext character then, the mapping is as follows:

D["y"]="E"
D["m"]="T"
D["e"]="H"
D["a"]="S"
D["w"]="I"
D["h"]="N"
D["s"]="R"
D["r"]="G"
D["p"]="A"
D["g"]="O"
D["j"]="M"
D["t"]="F"
D["i"]="C"
D["b"]="V"
D["o"]="B"
D["k"]="L"
D["v"]="W"
D["f"]="P"
D["n"]="U"
D["x"]="Y"
D["u"]="D"
D["d"]="Q"
D["8"]="4"
D["0"]="6"
D["3"]="9"
