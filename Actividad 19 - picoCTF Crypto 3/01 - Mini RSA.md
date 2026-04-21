#### Descripción 
What happens if you have a small exponent? There is a twist though, we padded the plaintext so that (M ** e) is just barely larger than N. Let's decrypt this:[values](https://challenge-files.picoctf.net/c_wily_courier/b61c2229204b98a71ea091b7f3c85b9520289448c2633b160d5f08a3f1bdadd3/values)

#### Solución
```
import gmpy2

n = 16157656843214630540782260519598878842336783177348929017407633211352136367960754624019502746024050951385898980

e = 3

c = 57097201750263178419445051663321827794197600311154322155634259018756200527916081633987502973042778864955373677

for i in range(1000000):
    m, is_root = gmpy2.iroot(i*n + c, e)
    if is_root:
        print("Found i:", i)
        hex_m = format(m, 'x')
        if len(hex_m) % 2:
            hex_m = '0' + hex_m
        print("Flag:", bytearray.fromhex(hex_m).decode())
        break
        
SebAcuna-picoctf@webshell:~/Cryptography$ python3 exp.py
Found i: 0
Flag:                                                                                                        picoCTF{e_sh0u1d_b3_lArg3r_92f4d5a5}

```
#### Notas
#### Referencias
