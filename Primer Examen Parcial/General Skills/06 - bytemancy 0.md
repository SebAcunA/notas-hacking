#### Descripción 
Can you conjure the right bytes? The program's source code can be downloaded [here](https://challenge-files.picoctf.net/c_candy_mountain/a32ca0e42d9494e3cf81e345699e8ae50415274c00871b1e8594d0fa0ce7078c/app.py).Connect to the program with netcat:`$ nc candy-mountain.picoctf.net 60854`
#### Solución
```
SebAcuna-picoctf@webshell:~$ uL_d1fdbdd0}
-bash: uL_d1fdbdd0}: command not found
SebAcuna-picoctf@webshell:~$ nc candy-mountain.picoctf.net 60854
⊹──────[ BYTEMANCY-0 ]──────⊹
☍⟐☉⟊☽☈⟁⧋⟡☍⟐☉⟊☽☈⟁⧋⟡☍⟐☉⟊☽☈⟁⧋⟡☍⟐

Send me ASCII DECIMAL 101, 101, 101, side-by-side, no space.

☍⟐☉⟊☽☈⟁⧋⟡☍⟐☉⟊☽☈⟁⧋⟡☍⟐☉⟊☽☈⟁⧋⟡☍⟐
⊹─────────────⟡─────────────⊹
==> eee
picoCTF{pr1n74813_ch4r5_62360bfd}
```
#### Notas
Simple, seguir las instrucciones el caracter 101 es "e" y lo escribimos 3 veces sin espacio
#### Referencias