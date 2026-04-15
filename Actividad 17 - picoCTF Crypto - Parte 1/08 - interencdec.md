#### Descripción 
#### Solución
```
┌──(kali㉿kali)-[~/picoctf/Cryptography/interencdec]
└─$ cat enc_flag
YidkM0JxZGtwQlRYdHFhR3g2YUhzZmF6TnFlVGwzWVR0clgyZzBOMm8yYXpZNWZRPT0nCg==

From Base64:
b'd3BqdkpBTXtqaGx6aHsfazNqeTl3YTtrX2g0N2o2azY5fQ=='
SE TIENE QUE COPIAR SOLO ESTO 
d3BqdkpBTXtqaGx6aHsfazNqeTl3YTtrX2g0N2o2azY5fQ==

From Base64:
wpjvJAM{jhlzhy_k3jy9wa3k_h47j6k69}

Caesar cipher:
picoCTF{caesar_d3cr9pt3d_a47c6d69}
```
#### Notas

#### Referencias
https://gchq.github.io/CyberChef/#recipe=From_Base64('A-Za-z0-9%2B/%3D',true,false)&input=ZDNCcWRrcEJUWHRxYUd4NmFIc2Zhek5xZVRsM1lUdHJYMmcwTjJvMmF6WTVmUT09&ieol=CRLF

https://www.dcode.fr/caesar-cipher