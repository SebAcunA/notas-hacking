#### Descripción 
How about some hide and seek heh?
Look at this image [here](https://artifacts.picoctf.net/c/241/atbash.jpg).
#### Solución
```
┌──(kali㉿kali)-[~/picoctf/Cryptography/hidetosee]
└─$ ls
atbash.jpg  encrypted.txt
                                                                                                                                                                                                                                            
┌──(kali㉿kali)-[~/picoctf/Cryptography/hidetosee]
└─$ steghide atbash.jpg
steghide: unknown command "atbash.jpg".
steghide: type "steghide --help" for help.
                                                                                                                                                                                                                                            
┌──(kali㉿kali)-[~/picoctf/Cryptography/hidetosee]
└─$ cat encrypted.txt                                
krxlXGU{zgyzhs_xizxp_7142uwv9}

Encriptación tipo atbash como lo dice el nombre del programa.
Vamos al cyberchef y pegamos el contenido de encrypted.txt
```
#### Notas
flag:
picoCTF{atbash_crack_7142fde9}
#### Referencias
https://gchq.github.io/CyberChef/#recipe=Atbash_Cipher()&input=a3J4bFhHVXt6Z3l6aHNfeGl6eHBfNzE0MnV3djl9
