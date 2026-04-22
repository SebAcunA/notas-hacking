#### Descripción 
We found this weird message being passed around on the servers, we think we have a working decryption scheme.Download the message [here](https://artifacts.picoctf.net/c/127/message.txt).Take each number mod 37 and map it to the following character set: 0-25 is the alphabet (uppercase), 26-35 are the decimal digits, and 36 is an underscore.Wrap your decrypted message in the picoCTF flag format (i.e. `picoCTF{decrypted_message}`)
#### Solución
```
nano exp.py
with open('message.txt', 'r') as f:
    contenido = f.read()

elementos = contenido.split()

caracteres = "ABCDEFGHIJKLMNOPQRSTUVWXYZ0123456789_"

mensaje_descifrado = ""

for x in elementos:
    valor = int(x) % 37
    mensaje_descifrado += caracteres[valor]

print(mensaje_descifrado)

┌──(kali㉿kali)-[~/picoctf/Cryptography/basicmod1]
└─$ python3 exp.py
R0UND_N_R0UND_79C18FB
```
#### Notas

#### Referencias