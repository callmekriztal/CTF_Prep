# Classic Crackme 100

we are given a crackme elf file 
from strings crackme understood that it is a C file elf

opened in ghidra ,inspect the main function 

some kind of encrption is done on an hardcoded string
to reverse this we need to write a decryption algorithm 

wrote the decryption code in py and sumbitted it in the server

for i_0 in range(len_str):
    idx = i_0 % 255
    random1 = (secret1 & idx) + (secret1 & (idx >> 1))
    random2 = (random1 & secret2) + (secret2 & (random1 >> 2))
    r = (random2 & secret3) + (secret3 & (random2 >> 4))
    r_values.append(r)

this is the decryption algorithm