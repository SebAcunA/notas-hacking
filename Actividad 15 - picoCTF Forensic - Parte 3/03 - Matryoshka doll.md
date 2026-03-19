#### Descripción 
Matryoshka dolls are a set of wooden dolls of decreasing size placed one inside another. What's the final one?Image: [dolls.jpg](https://challenge-files.picoctf.net/c_wily_courier/feaddb84eaaa2f8d6b83bda9e7a9c46a86474361e095fea9ee3840873f3506b4/dolls.jpg)
#### Solución
```
┌──(kali㉿kali)-[~/forensic/Matryoshka]
└─$ wget https://challenge-files.picoctf.net/c_wily_courier/feaddb84eaaa2f8d6b83bda9e7a9c46a86474361e095fea9ee3840873f3506b4/dolls.jpg
--2026-03-19 04:39:43--  https://challenge-files.picoctf.net/c_wily_courier/feaddb84eaaa2f8d6b83bda9e7a9c46a86474361e095fea9ee3840873f3506b4/dolls.jpg
Resolving challenge-files.picoctf.net (challenge-files.picoctf.net)... 3.161.44.22, 3.161.44.103, 3.161.44.84, ...
Connecting to challenge-files.picoctf.net (challenge-files.picoctf.net)|3.161.44.22|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 651613 (636K) [application/octet-stream]
Saving to: ‘dolls.jpg’

dolls.jpg                 100%[==================================>] 636.34K  2.20MB/s    in 0.3s    

2026-03-19 04:39:44 (2.20 MB/s) - ‘dolls.jpg’ saved [651613/651613]

                                                                                                     
┌──(kali㉿kali)-[~/forensic/Matryoshka]
└─$ binwalk -e dolls.jpg

DECIMAL       HEXADECIMAL     DESCRIPTION
--------------------------------------------------------------------------------
272492        0x4286C         Zip archive data, at least v2.0 to extract, compressed size: 378933, uncompressed size: 383920, name: base_images/2_c.jpg

WARNING: One or more files failed to extract: either no utility was found or it's unimplemented

                                                                                                     
┌──(kali㉿kali)-[~/forensic/Matryoshka]
└─$ cd base_images
cd: no such file or directory: base_images
                                                                                                     
┌──(kali㉿kali)-[~/forensic/Matryoshka]
└─$ ls
dolls.jpg  _dolls.jpg.extracted
                                                                                                     
┌──(kali㉿kali)-[~/forensic/Matryoshka]
└─$ cd _dolls.jpg.extracted
                                                                                                     
┌──(kali㉿kali)-[~/forensic/Matryoshka/_dolls.jpg.extracted]
└─$ ls
4286C.zip  base_images
                                                                                                     
┌──(kali㉿kali)-[~/forensic/Matryoshka/_dolls.jpg.extracted]
└─$ cd base_images         
                                                                                                     
┌──(kali㉿kali)-[~/forensic/Matryoshka/_dolls.jpg.extracted/base_images]
└─$ ls
2_c.jpg
                                                                                                     
┌──(kali㉿kali)-[~/forensic/Matryoshka/_dolls.jpg.extracted/base_images]
└─$ binwalk -e 2_c.jpg  

DECIMAL       HEXADECIMAL     DESCRIPTION
--------------------------------------------------------------------------------
187707        0x2DD3B         Zip archive data, at least v2.0 to extract, compressed size: 196025, uncompressed size: 201427, name: base_images/3_c.jpg

WARNING: One or more files failed to extract: either no utility was found or it's unimplemented

                                                                                                     
┌──(kali㉿kali)-[~/forensic/Matryoshka/_dolls.jpg.extracted/base_images]
└─$ ls
2_c.jpg  _2_c.jpg.extracted
                                                                                                     
┌──(kali㉿kali)-[~/forensic/Matryoshka/_dolls.jpg.extracted/base_images]
└─$ cd _2_c.jpg.extracted
                                                                                                     
┌──(kali㉿kali)-[~/…/Matryoshka/_dolls.jpg.extracted/base_images/_2_c.jpg.extracted]
└─$ ls
2DD3B.zip  base_images
                                                                                                     
┌──(kali㉿kali)-[~/…/Matryoshka/_dolls.jpg.extracted/base_images/_2_c.jpg.extracted]
└─$ cd base_images       
                                                                                                     
┌──(kali㉿kali)-[~/…/_dolls.jpg.extracted/base_images/_2_c.jpg.extracted/base_images]
└─$ ls
3_c.jpg
                                                                                                     
┌──(kali㉿kali)-[~/…/_dolls.jpg.extracted/base_images/_2_c.jpg.extracted/base_images]
└─$ binwalk -e 3_c.jpg

DECIMAL       HEXADECIMAL     DESCRIPTION
--------------------------------------------------------------------------------
123606        0x1E2D6         Zip archive data, at least v2.0 to extract, compressed size: 77633, uncompressed size: 79786, name: base_images/4_c.jpg

WARNING: One or more files failed to extract: either no utility was found or it's unimplemented

                                                                                                     
┌──(kali㉿kali)-[~/…/_dolls.jpg.extracted/base_images/_2_c.jpg.extracted/base_images]
└─$ cd base_images
cd: no such file or directory: base_images
                                                                                                     
┌──(kali㉿kali)-[~/…/_dolls.jpg.extracted/base_images/_2_c.jpg.extracted/base_images]
└─$ ls
3_c.jpg  _3_c.jpg.extracted
                                                                                                     
┌──(kali㉿kali)-[~/…/_dolls.jpg.extracted/base_images/_2_c.jpg.extracted/base_images]
└─$ cd _3_c.jpg.extracted; cd base_images
                                                                                                     
┌──(kali㉿kali)-[~/…/_2_c.jpg.extracted/base_images/_3_c.jpg.extracted/base_images]
└─$ ls
4_c.jpg
                                                                                                     
┌──(kali㉿kali)-[~/…/_2_c.jpg.extracted/base_images/_3_c.jpg.extracted/base_images]
└─$ binwalk -e 4_c.jpg                   

DECIMAL       HEXADECIMAL     DESCRIPTION
--------------------------------------------------------------------------------
79578         0x136DA         Zip archive data, at least v1.0 to extract, compressed size: 42, uncompressed size: 42, name: flag.txt

WARNING: One or more files failed to extract: either no utility was found or it's unimplemented
                   
┌──(kali㉿kali)-[~/…/_2_c.jpg.extracted/base_images/_3_c.jpg.extracted/base_images]
└─$ cd _4_c.jpg.extracted; cd base_images
cd: no such file or directory: base_images
                                                                                                     
┌──(kali㉿kali)-[~/…/base_images/_3_c.jpg.extracted/base_images/_4_c.jpg.extracted]
└─$ ls
136DA.zip  flag.txt
                                                                                                     
┌──(kali㉿kali)-[~/…/base_images/_3_c.jpg.extracted/base_images/_4_c.jpg.extracted]
└─$ open flag.txt
                                                                                                     
┌──(kali㉿kali)-[~/…/base_images/_3_c.jpg.extracted/base_images/_4_c.jpg.extracted]
```
#### Notas
#### Referencias
