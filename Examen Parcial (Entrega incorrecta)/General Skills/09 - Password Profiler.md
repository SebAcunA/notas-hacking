#### Descripción 
We intercepted a suspicious file from a system, but instead of the password itself, it only contains its SHA-1 hash. Using OSINT techniques, you are provided with personal details about the target. Your task is to leverage this information to generate a custom password list and recover the original password by matching its hash.Download the following files:
[userinfo](https://challenge-files.picoctf.net/c_plain_mesa/3c16fb8e48ddae444f6840e81660a5a8cb2d30b69092b04f619d6ac34676a919/userinfo.txt): Contains the personal details.
[hash](https://challenge-files.picoctf.net/c_plain_mesa/3c16fb8e48ddae444f6840e81660a5a8cb2d30b69092b04f619d6ac34676a919/hash.txt): Contains the SHA-1 hash of the password.
[check_password](https://challenge-files.picoctf.net/c_plain_mesa/3c16fb8e48ddae444f6840e81660a5a8cb2d30b69092b04f619d6ac34676a919/check_password.py): Script to test passwords against the hash.
#### Solución
```
SebAcuna-picoctf@webshell:~$ git clone https://github.com/Mebus/cupp.git
Cloning into 'cupp'...
remote: Enumerating objects: 261, done.
remote: Counting objects: 100% (95/95), done.
remote: Compressing objects: 100% (26/26), done.
remote: Total 261 (delta 84), reused 69 (delta 69), pack-reused 166 (from 2)
Receiving objects: 100% (261/261), 2.16 MiB | 1.80 MiB/s, done.
Resolving deltas: 100% (142/142), done.
SebAcuna-picoctf@webshell:~$ cd cupp
SebAcuna-picoctf@webshell:~/cupp$ 
SebAcuna-picoctf@webshell:~/cupp$ # 2. Corre CUPP en modo interactivo
SebAcuna-picoctf@webshell:~/cupp$ python3 cupp.py -i
 ___________ 
   cupp.py!                 # Common
      \                     # User
       \   ,__,             # Passwords
        \  (oo)____         # Profiler
           (__)    )\   
              ||--|| *      [ Muris Kurgas | j0rgan@remote-exploit.org ]
                            [ Mebus | https://github.com/Mebus/]


[+] Insert the information about the victim to make a dictionary
[+] If you don't know all the info, just hit enter when asked! ;)

> First Name:
```
#### Notas
el código solo funciona consultando un txt con los posibles nombres y contraseñas, generarlos manualmente es muy tedioso y se podría decir casi imposible, pero existe una herramienta al que se le pasan tipos comunes como el nombre y prueba combinaciones probables. Las personas somos muy dadas a poner fechas de cumpleaños o cosas faciles de recordar en contraseñas por lo que este programa puede ser peligroso para aquellas personas que no pones una brecha de seguridad un poco mas alta
#### Referencias
