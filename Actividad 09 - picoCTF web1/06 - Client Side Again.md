#### Descripción 
Can you break into this super secure portal?
http://fickle-tempest.picoctf.net:63835
#### Solución
```
- El arreglo _0x5a46 contiene las cadenas importantes:
['daf93}', '_again_4', 'this', "Password Verified", "Incorrect password", 
'getElementById', 'value', 'substring', 'picoCTF{', 'not_this']
- La función verify() compara fragmentos de la contraseña con esas cadenas.
- Las condiciones verifican que la contraseña tenga la forma de una bandera de picoCTF.
Condiciones clave
- checkpass.substring(0, 8) == "picoCTF{"
- checkpass.substring(3, 6) == "oCT"
- checkpass.substring(6, 11) == "F{not"
- checkpass.substring(7, 9) == "{n"
- checkpass.substring(8, 16) == "not_this"
- checkpass.substring(12, 16) == "_again_4"
- checkpass.substring(16, 21) == "daf93}"
  
  Bandera en orden: picoCTF{not_this_again_4daf93}
```
#### Notas
Fue necesario aprender sobre obfuscación
#### Referencias
https://promon.io/resources/security-software-glossary/deobfuscation
https://obf-io.deobfuscate.io/
