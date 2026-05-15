#### Descripción 
There's a flag shop selling stuff, can you buy a flag?

[Source](https://challenge-files.picoctf.net/c_fickle_tempest/3b8dcb92959510cff4c72e182cec42febd0b32bd1911c385e3a4a74a03181e9d/store.c). Connect with nc fickle-tempest.picoctf.net 54602.
#### Solución
```
rosyperez@MacBookAir flag_shop % nc fickle-tempest.picoctf.net 60991 
Welcome to the flag exchange
We sell flags
1. Check Account Balance
2. Buy Flags
3. Exit
 Enter a menu selection
2
Currently for sale
4. Defintely not the flag Flag
5. 1337 Flag
1
These knockoff Flags cost 900 each, enter desired quantity
2400000

The final cost is: -2134967296

Your current balance after transaction: 2134968396
  
Welcome to the flag exchange
We sell flags

1. Check Account Balance
2. Buy Flags
3. Exit
 Enter a menu selection
2
Currently for sale
4. Defintely not the flag Flag
5. 1337 Flag
2
1337 flags cost 100000 dollars, and we only have 1 in stock
Enter 1 to buy one1
YOUR FLAG IS: picoCTF{m0n3y_bag5_F2Eb382F}
rosyperez@MacBookAir flag_shop %
```
#### Notas
  ```
  900 × 2,400,000 = 2,160,000,000  →  desborda a -2,134,967,296
balance = 1100 - (-2,134,967,296) = 2,134,968,396  ✓ > 100,000
  ```
#### Referencias
https://www.youtube.com/watch?v=2dWfakv5uBQ