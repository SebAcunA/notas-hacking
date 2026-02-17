#### Descripción 
Find the flag in the Python script![Download Python script](https://artifacts.picoctf.net/c/37/serpentine.py)
#### Solución
```
NameError: name 'printflag' is not defined. Did you mean: 'print_flag'?
SebAcuna-picoctf@webshell:~$ nano serpentine.py
SebAcuna-picoctf@webshell:~$ python serpentine.py

    Y
  .-^-.
 /     \      .- ~ ~ -.
()     ()    /   _ _   `.                     _ _ _
 \_   _/    /  /     \   \                . ~  _ _  ~ .
   | |     /  /       \   \             .' .~       ~-. `.
   | |    /  /         )   )           /  /             `.`.
   \ \_ _/  /         /   /           /  /                `'
    \_ _ _.'         /   /           (  (
                    /   /             \  \
                   /   /               \  \
                  /   /                 )  )
                 (   (                 /  /
                  `.  `.             .'  /
                    `.   ~ - - - - ~   .'
                       ~ . _ _ _ _ . ~

Welcome to the serpentine encourager!


a) Print encouragement
b) Print flag
c) Quit

What would you like to do? (a/b/c) b
picoCTF{7h3_r04d_l355_7r4v3l3d_8e47d128}
a) Print encouragement
b) Print flag
c) Quit

What would you like to do? (a/b/c) ^CTraceback (most recent call last):
  File "/home/SebAcuna-picoctf/serpentine.py", line 80, in <module>
    main()
  File "/home/SebAcuna-picoctf/serpentine.py", line 63, in main
    choice = input('What would you like to do? (a/b/c) ')
KeyboardInterrupt

SebAcuna-picoctf@webshell:~$ 
```
#### Notas
#### Referencias

