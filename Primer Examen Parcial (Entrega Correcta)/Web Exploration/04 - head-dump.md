#### Descripción 
Welcome to the challenge! In this challenge, you will explore a web application and find an endpoint that exposes a file containing a hidden flag.The application is a simple blog website where you can read articles about various topics, including an article about API Documentation. Your goal is to explore the application and find the endpoint that generates files holding the server’s memory, where a secret flag is hidden.The website is running [picoCTF News](http://verbal-sleep.picoctf.net:58762/).
#### Solución
```
checar la interfaz de la página web y entrar a esta extensión
http://verbal-sleep.picoctf.net:50530/api-docs/#/Diagnosing/get_heapdump

descargar el archivo y leerlo
```
#### Notas
A veces la respuesta no es tan rebuscada como nosotros pensamos
#### Referencias