#### Descripción 
Why use p and q when I can use more?
Connect with nc fickle-tempest.picoctf.net 63151.
#### Solución
Para resolver el reto utilizamos un **RSA decoder**. El procedimiento consistió en obtener los valores de `n`, `e` y el ciphertext proporcionado por el reto. Sin embargo, el decoder por sí solo no podía avanzar sin conocer la clave privada.  
Por ello, realizamos un paso adicional: **factorizar `n`**. Al descomponer `n` en sus factores primos `p` y `q`, pudimos calcular el valor de `φ(n)` y posteriormente obtener la clave privada `d` mediante la inversa modular de `e`. Con `d` ya disponible, el decoder pudo descifrar el mensaje correctamente.

#### Notas
En RSA, la seguridad depende de la dificultad de factorizar `n`, que es el producto de dos números primos grandes (`p` y `q`).  
El motivo por el cual fue necesario factorizar `n` en este reto es que, sin conocer `p` y `q`, no es posible calcular `φ(n)` ni derivar la clave privada `d`. El decoder necesita esa clave para descifrar el ciphertext.  
En un sistema RSA real, `n` se elige lo suficientemente grande para que factorizarlo sea computacionalmente inviable. Sin embargo, en retos de CTF como este, `n` suele ser pequeño o diseñado para que la factorización sea posible con herramientas de fuerza bruta o algoritmos conocidos, permitiendo así completar el desafío.
#### Referencias
https://www.youtube.com/watch?v=-EXKqVfYmCU