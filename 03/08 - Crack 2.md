#### Descripción 
Can you crack the password to get the flag?Download the password checker [here](https://artifacts.picoctf.net/c/13/level2.py) and you'll need the encrypted [flag](https://artifacts.picoctf.net/c/13/level2.flag.txt.enc) in the same directory too.
#### Solución
```
SebAcuna-picoctf@webshell:~$ python level2.py
Please enter correct password for flag: hi
That password is incorrect
SebAcuna-picoctf@webshell:~$ nano level2.py
SebAcuna-picoctf@webshell:~$ python level2.py
  File "/home/SebAcuna-picoctf/level2.py", line 15
    print ("The password is: " + 0x64) + chr(0x65) + chr(0x37) + chr(0x36))
                                                                          ^
SyntaxError: unmatched ')'
SebAcuna-picoctf@webshell:~$ nano level2.py
SebAcuna-picoctf@webshell:~$ python level2.py
The password is: de76
Please enter correct password for flag: de76
}Welcome back... your flag, user:
```
#### Notas
#### Referencias