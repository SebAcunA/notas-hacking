#### Descripción 
Find the flag being held on this server to get ahead of the competition
http://wily-courier.picoctf.net:59015/
#### Solución
```
SebAcuna-picoctf@webshell:~$ curl HEAD -I http://wily-courier.picoctf.net:59015/
curl: (6) Could not resolve host: HEAD
HTTP/1.1 200 OK
Date: Sat, 28 Feb 2026 20:16:16 GMT
Server: Apache/2.4.38 (Debian)
X-Powered-By: PHP/7.2.34
flag: picoCTF{r3j3ct_th3_du4l1ty_8b13f07}
Content-Type: text/html; charset=UTF-8
```
#### Notas
También se puede hacer con la interface de burpsuite recibiendo intercepciones y modificandolas en el apartado de Repeater
#### Referencias
https://www.youtube.com/watch?v=oiZk0tIkR48&list=PLDo9DMLZyP6kTZ8Td37-LdbAx4-yNfHBl&index=11