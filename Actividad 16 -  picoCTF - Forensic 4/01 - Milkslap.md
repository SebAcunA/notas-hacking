#### Descripción 
🥛http://wily-courier.picoctf.net:50134/
#### Solución
```
┌──(kali㉿kali)-[~/forensic/milkslape]
└─$ RUBY_THREAD_VM_STACK_SIZE=500000000 zsteg -s all *.png | grep pico
b1,b,lsb,xy         .. text: "picoCTF{imag3_m4n1pul4t10n_sl4p5}\n"

```
#### Notas
#### Referencias