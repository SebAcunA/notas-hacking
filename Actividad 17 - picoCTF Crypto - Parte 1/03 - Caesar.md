#### Descripción 
Decrypt this message.Message: 
[message](https://challenge-files.picoctf.net/c_fickle_tempest/6c40a1814a02fcc4bb567552d918c53b4b15a1b81518ec0ef7447fbfb73a3ce9/data.enc)
#### Solución
```
┌──(kali㉿kali)-[~/picoctf/Cryptography]
└─$ cd cesar       
                                                            
┌──(kali㉿kali)-[~/picoctf/Cryptography/cesar]
└─$ ls
data.enc  exp.py
                                                            
┌──(kali㉿kali)-[~/picoctf/Cryptography/cesar]
└─$ nano exp.py 
                                                            
┌──(kali㉿kali)-[~/picoctf/Cryptography/cesar]
└─$ python3 exp.py 
Trying all rotations:
------------------------------
ROT 00: picoCTF{rgdhhxcviwtgjqxrdcbxpotman}
ROT 01: picoCTF{sheiiydwjxuhkrysedcyqpunbo}
ROT 02: picoCTF{tifjjzexkyvilsztfedzrqvocp}
ROT 03: picoCTF{ujgkkafylzwjmtaugfeasrwpdq}
ROT 04: picoCTF{vkhllbgzmaxknubvhgfbtsxqer}
ROT 05: picoCTF{wlimmchanbylovcwihgcutyrfs}
ROT 06: picoCTF{xmjnndiboczmpwdxjihdvuzsgt}
ROT 07: picoCTF{ynkooejcpdanqxeykjiewvathu}
ROT 08: picoCTF{zolppfkdqeboryfzlkjfxwbuiv}
ROT 09: picoCTF{apmqqglerfcpszgamlkgyxcvjw}
ROT 10: picoCTF{bqnrrhmfsgdqtahbnmlhzydwkx}
ROT 11: picoCTF{crossingtherubiconmiazexly}
ROT 12: picoCTF{dspttjohuifsvcjdponjbafymz}
ROT 13: picoCTF{etquukpivjgtwdkeqpokcbgzna}
ROT 14: picoCTF{furvvlqjwkhuxelfrqpldchaob}
ROT 15: picoCTF{gvswwmrkxlivyfmgsrqmedibpc}
ROT 16: picoCTF{hwtxxnslymjwzgnhtsrnfejcqd}
ROT 17: picoCTF{ixuyyotmznkxahoiutsogfkdre}
ROT 18: picoCTF{jyvzzpunaolybipjvutphglesf}
ROT 19: picoCTF{kzwaaqvobpmzcjqkwvuqihmftg}
ROT 20: picoCTF{laxbbrwpcqnadkrlxwvrjinguh}
ROT 21: picoCTF{mbyccsxqdrobelsmyxwskjohvi}
ROT 22: picoCTF{nczddtyrespcfmtnzyxtlkpiwj}
ROT 23: picoCTF{odaeeuzsftqdgnuoazyumlqjxk}
ROT 24: picoCTF{pebffvatgurehovpbazvnmrkyl}
ROT 25: picoCTF{qfcggwbuhvsfipwqcbawonslzm}

import string
import re

# Use 'lowercase' specifically to avoid index issues with 'ascii_letters'
abc = string.ascii_lowercase

with open('data.enc', 'r') as f:
    contenido = f.read()

# Fix the warning with a raw string 'r'
encriptado = re.findall(r'\{(.*?)\}', contenido)[0]

print("Trying all rotations:")
print("-" * 30)

for rot in range(26):
    salida = ''
    for car in encriptado:
        if car in abc:
            # Find current index, add rotation, and wrap around 26
            index = abc.find(car)
            salida += abc[(index + rot) % 26]
        else:
            # Keep numbers/underscores as they are
            salida += car
    
    print(f"ROT {rot:02}: picoCTF{{{salida}}}")
```
#### Notas
ROT 11: picoCTF{crossingtherubiconmiazexly}
#### Referencias