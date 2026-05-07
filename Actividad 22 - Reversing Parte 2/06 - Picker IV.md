#### Descripción 
Can you figure out how this program works to get the flag?Connect to the program with netcat:`$ nc saturn.picoctf.net 55537`The program's source code can be downloaded [here](https://artifacts.picoctf.net/c/527/picker-IV.c). The binary can be downloaded [here](https://artifacts.picoctf.net/c/527/picker-IV).
#### Solución
Al analizar el binario, se observó que el programa permite al usuario ingresar una dirección de memoria en hexadecimal para realizar un salto directo hacia dicha dirección.  
  
Primero se utilizó `nm` para localizar la dirección de la función `win`, encargada de imprimir la bandera:
``` 
rosyperez@MacBookAir PickerIV % nm picker-IV | grep win    
000000000040129e T win
rosyperez@MacBookAir PickerIV % nc saturn.picoctf.net 55537
Enter the address in hex to jump to, excluding '0x': 40129e
You input 0x40129e
You won!
picoCTF{n3v3r_jump_t0_u53r_5uppl13d_4ddr35535_01672a61}
```
#### Notas
este estuvo imposible
- `nm` permite listar los símbolos presentes dentro de un binario.  
- La letra `T` indica que la función se encuentra en la sección de código ejecutable (`.text`).  
- La función `win()` ya existía dentro del programa; únicamente fue necesario saltar a ella.  
  
---
#### Referencias
