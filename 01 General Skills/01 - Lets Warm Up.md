#### Descripción 
If I told you a word started with 0x70 in hexadecimal, what would it start with in ASCII?

#### Solución
```
>>> bytearray.fromhex("70").decode()
'p'
```
#### Notas


#### Referencias
https://stackoverflow.com/questions/9641440/convert-from-ascii-string-encoded-in-hex-to-plain-ascii
