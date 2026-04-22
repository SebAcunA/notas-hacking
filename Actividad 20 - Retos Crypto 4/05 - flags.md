#### Descripción 
What do the [flags](https://challenge-files.picoctf.net/c_fickle_tempest/214c9d918be75903d4183c35fa4b94ef60dba05fc4df37c97cf0868087067372/flag.png) mean?
#### Solución
 
 ### 1. Identificar el tipo de banderas  
 Las banderas corresponden al código de señales marítimas internacionales.
---  
  ### 2. Decodificación  
Se utilizó un decodificador en línea de banderas náuticas (o una tabla de referencia) para traducir cada bandera a su letra correspondiente.  
  
Al decodificar la secuencia completa se obtiene:
F1AG5AND5TUFF
```bash  
picoCTF{F1AG5AND5TUFF}
```
#### Notas

#### Referencias
https://www.dcode.fr/maritime-signals-code