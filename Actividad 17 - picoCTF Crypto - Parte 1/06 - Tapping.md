#### Descripción 
Theres tapping coming in from the wires.
What's it saying nc fickle-tempest.picoctf.net 49387.
#### Solución
```
┌──(kali㉿kali)-[~/picoctf/Cryptography]
└─$ nc fickle-tempest.picoctf.net 49387.
.--. .. -.-. --- -.-. - ..-. { -- ----- .-. ... ...-- -.-. ----- -.. ...-- .---- ... ..-. ..- -. ...-- ---.. --... ....- ----- --... ---.. -.-. } 


Resultado de la desencriptación del código morse
PICOCTFM0RS3C0D31SFUN3874078C

```
#### Notas
la llave no se traduce literal porque no existen los parentesis que abren y cierran en morse por lo que la llave real es:
`
`picoCTF{M0RS3C0D31SFUN3874078C}
#### Referencias
https://gchq.github.io/CyberChef/#recipe=From_Morse_Code('Space','Line%20feed')&input=Li0tLiAuLiAtLi0uIC0tLSAtLi0uIC0gLi4tLiB7IC0tIC0tLS0tIC4tLiAuLi4gLi4uLS0gLS4tLiAtLS0tLSAtLi4gLi4uLS0gLi0tLS0gLi4uIC4uLS4gLi4tIC0uIC4uLi0tIC0tLS4uIC0tLi4uIC4uLi4tIC0tLS0tIC0tLi4uIC0tLS4uIC0uLS4gfQ&oenc=65001&ieol=CRLF&oeol=CRLF