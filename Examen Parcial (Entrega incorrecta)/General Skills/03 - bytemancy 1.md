#### Descripción 
Can you conjure the right bytes? The program's source code can be downloaded [here](https://challenge-files.picoctf.net/c_foggy_cliff/89d4e001a32151c23b9ad54e9f12939e30d20903b113433cbd5e65df11ffabf7/app.py).Connect to the program with netcat:`$ nc foggy-cliff.picoctf.net 56265`
#### Solución
```
⊹──────[ BYTEMANCY-1 ]──────⊹
☍⟐☉⟊☽☈⟁⧋⟡☍⟐☉⟊☽☈⟁⧋⟡☍⟐☉⟊☽☈⟁⧋⟡☍⟐

Send me ASCII DECIMAL 101 1751 times, side-by-side, no space.

☍⟐☉⟊☽☈⟁⧋⟡☍⟐☉⟊☽☈⟁⧋⟡☍⟐☉⟊☽☈⟁⧋⟡☍⟐
⊹─────────────⟡─────────────⊹
==> ^C
SebAcuna-picoctf@webshell:~$ python3 -c "print('e' * 1751)" | nc foggy-cliff.picoctf.net 56265
⊹──────[ BYTEMANCY-1 ]──────⊹
☍⟐☉⟊☽☈⟁⧋⟡☍⟐☉⟊☽☈⟁⧋⟡☍⟐☉⟊☽☈⟁⧋⟡☍⟐

Send me ASCII DECIMAL 101 1751 times, side-by-side, no space.

☍⟐☉⟊☽☈⟁⧋⟡☍⟐☉⟊☽☈⟁⧋⟡☍⟐☉⟊☽☈⟁⧋⟡☍⟐
⊹─────────────⟡─────────────⊹
RESPUESTA ==> picoCTF{h0w_m4ny_e's???_7dbc095c}

while(True):
  try:
    print('⊹──────[ BYTEMANCY-1 ]──────⊹')
    print("☍⟐☉⟊☽☈⟁⧋⟡☍⟐☉⟊☽☈⟁⧋⟡☍⟐☉⟊☽☈⟁⧋⟡☍⟐")
    print()
    print('Send me ASCII DECIMAL 101 1751 times, side-by-side, no space.')
    print()
    print("☍⟐☉⟊☽☈⟁⧋⟡☍⟐☉⟊☽☈⟁⧋⟡☍⟐☉⟊☽☈⟁⧋⟡☍⟐")
    print('⊹─────────────⟡─────────────⊹')
    user_input = input('==> ')
    if user_input == "\x65"*1751:
      print(open("./flag.txt", "r").read())
      break
    else:
      print("That wasn't it. I got: " + str(user_input))
      print()
      print()
      print()
  except Exception as e:
    print(e)
    break

```
#### Notas
El problema tenía 3 o 4 diferentes soluciones, a mi me tocó  el problema imprime el caracter 101 1751 veces por lo que para romperar la lógica tuve que entrar al programa que se nos daba a descargar, después la solución estaba en el if y la condición que si cumpli lo que decía en el texto, para lograr escribir esta cantidad de caracteres aprovechamos que python está disponible desde la terminal , imprimimos los caracteres que nos dice con Python print() y la concatenamos con la conexión al servidor 
#### Referencias
https://medium.com/@bayrakerenes/picoctf-2026-write-up-general-skills-kategorisinde-6-soru-50ecced1596e