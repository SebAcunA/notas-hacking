#### Descripción 
Can you crack the password to get the flag?Download the password checker [here](https://artifacts.picoctf.net/c/12/level1.py) and you'll need the encrypted [flag](https://artifacts.picoctf.net/c/12/level1.flag.txt.enc) in the same directory too.
#### Solución
```
SebAcuna-picoctf@webshell:~$ ls
level1.flag.txt.enc  level1.py
SebAcuna-picoctf@webshell:~$ nano level1.py
SebAcuna-picoctf@webshell:~$ python level1.py
Please enter correct password for flag: 8713
Welcome back... your flag, user:
picoCTF{545h_r1ng1ng_1b2fd683}
```
#### Notas
#### Referencias
