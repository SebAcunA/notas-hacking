#### Descripción 
Find the flag in this [picture](https://challenge-files.picoctf.net/c_fickle_tempest/fea53d4b5a95f9e78fc25c77dd5332d9ef4aa71d2e64ea96bbe171e0300741b2/pico_img.png).
#### Solución
```
┌──(kali㉿kali)-[~/picoctf/forensinc/someta]
└─$ wget https://challenge-files.picoctf.net/c_fickle_tempest/fea53d4b5a95f9e78fc25c77dd5332d9ef4aa71d2e64ea96bbe171e0300741b2/pico_img.png
--2026-03-09 10:18:19--  https://challenge-files.picoctf.net/c_fickle_tempest/fea53d4b5a95f9e78fc25c77dd5332d9ef4aa71d2e64ea96bbe171e0300741b2/pico_img.png
Resolving challenge-files.picoctf.net (challenge-files.picoctf.net)... 18.238.132.26, 18.238.132.88, 18.238.132.115, ...
Connecting to challenge-files.picoctf.net (challenge-files.picoctf.net)|18.238.132.26|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 108795 (106K) [application/octet-stream]
Saving to: ‘pico_img.png’

pico_img.png        100%[================>] 106.25K   476KB/s    in 0.2s    

2026-03-09 10:18:20 (476 KB/s) - ‘pico_img.png’ saved [108795/108795]

                                                                             
┌──(kali㉿kali)-[~/picoctf/forensinc/someta]
└─$ ls
pico_img.png
                                                                             
┌──(kali㉿kali)-[~/picoctf/forensinc/someta]
└─$ exiftool pico_img.png -Artist
Artist                          : picoCTF{s0_m3ta_bc056477}

```
#### Notas
#### Referencias
