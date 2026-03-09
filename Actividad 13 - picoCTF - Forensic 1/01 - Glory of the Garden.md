#### Descripción 
This file contains more than it seems.Get the flag from [garden.jpg](https://challenge-files.picoctf.net/c_fickle_tempest/39ad2588c3c0db341eff579d7cf894efc34a3b8174368eee2ea0e5ea06516238/garden.jpg).
#### Solución
```
┌──(kali㉿kali)-[~/picoctf/forensinc/01]
└─$ wget https://challenge-files.picoctf.net/c_fickle_tempest/39ad2588c3c0db341eff579d7cf894efc34a3b8174368eee2ea0e5ea06516238/garden.jpg   
--2026-03-09 11:06:14--  https://challenge-files.picoctf.net/c_fickle_tempest/39ad2588c3c0db341eff579d7cf894efc34a3b8174368eee2ea0e5ea06516238/garden.jpg
Resolving challenge-files.picoctf.net (challenge-files.picoctf.net)... 18.238.132.88, 18.238.132.115, 18.238.132.49, ...
Connecting to challenge-files.picoctf.net (challenge-files.picoctf.net)|18.238.132.88|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 2295191 (2.2M) [application/octet-stream]
Saving to: ‘garden.jpg’

garden.jpg                   100%[==============================================>]   2.19M  1.49MB/s    in 1.5s    

2026-03-09 11:06:16 (1.49 MB/s) - ‘garden.jpg’ saved [2295191/2295191]

                                                                                                                    
┌──(kali㉿kali)-[~/picoctf/forensinc/01]
└─$ sudo apt install ghex
[sudo] password for kali: 
Error: Unable to locate package ghex
                                                                                                                    
┌──(kali㉿kali)-[~/picoctf/forensinc/01]
└─$ xxd flag.png | less  

xxd: flag.png: No such file or directory
                                                                                                                    
┌──(kali㉿kali)-[~/picoctf/forensinc/01]
└─$ ls   
fasdfasdfasdf  garden.jpg
                                                                                                                    
┌──(kali㉿kali)-[~/picoctf/forensinc/01]
└─$ xxd garden.jpg | less

                                                                                                                    
┌──(kali㉿kali)-[~/picoctf/forensinc/01]
└─$ xxd garden.jpg       

```
#### Notas
cancelé todas la cadena de caracteres que me estaba generando con ctrl+c y estaba justo al final en este formato
```
00230550: a2bb bdac 9687 98e4 d3b2 e87f ffd9 4865  ..............He
00230560: 7265 2069 7320 6120 666c 6167 3a20 7069  re is a flag: pi
00230570: 636f 4354 467b 6d6f 7265 5f74 6861 6e5f  coCTF{more_than_
00230580: 6d33 3374 735f 7468 655f 3379 3333 3963  m33ts_the_3y339c
00230590: 6265 3664 637d 0a                        be6dc}.

```
#### Referencias
