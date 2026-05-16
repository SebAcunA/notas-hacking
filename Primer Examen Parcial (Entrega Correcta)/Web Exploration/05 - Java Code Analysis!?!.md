#### Descripción 
BookShelf Pico, my premium online book-reading service.
I believe that my website is super secure. I challenge you to prove me wrong by reading the 'Flag' book!
Here are the credentials to get you started:
- Username: "user"
- Password: "user"
Source code can be downloaded [here](https://artifacts.picoctf.net/c/483/bookshelf-pico.zip).
Website can be accessed [here!](http://saturn.picoctf.net:56593/).
#### Solución
1. Descargamos y analizamos el código fuente proporcionado en Java (basado en Spring Boot).
2. Revisamos el archivo `src/main/java/io/github/nandandesai/pico/security/SecretGenerator.java` y descubrimos una vulnerabilidad crítica: la clave secreta para firmar los tokens JWT está fija (hardcodeada) en el código y siempre es el valor `"1234"`.
3. java:
    private String generateRandomString(int len) {
        // not so random
        return "1234";
    }
4. Analizamos los archivos `data.sql` y `BookShelfConfig.java` para deducir cómo están estructurados los usuarios. Notamos que el rol de Administrador (`Admin`) está asignado a un usuario cuyo `userId` es el número `2` y su correo es `admin`.
5. Colocamos en LocalStorage este 
`authToken:`
```
eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpc3MiOiJib29rc2hlbGYiLCJpYXQiOjE3Nzg4OTIwNjAsImV4cCI6MTc3OTQ5Njg2MCwidXNlcklkIjoyLCJlbWFpbCI6ImFkbWluIiwicm9sZSI6IkFkbWluIn0.1vRSnYk3DNRO2YHjorwXe5X3LeUhnc0pZfYN8HO3ACg
```
y este 
`token-payload:`
```
{"iss":"bookshelf","iat":1778892060,"exp":1779496860,"userId":2,"email":"admin","role":"Admin"}
```
#### Notas
- Un error muy común en este reto es colocar el `userId` como texto (ej. `"2"`) dentro del JSON. Cuando el código Java (`JwtService.java`) intenta convertir esto a `Int`, falla, devolviendo un valor nulo. Esto provoca que el controlador crashee arrojando un Error 500 ("Failed to load the dashboard").
- El valor `tokenPayload` del _Local Storage_ solo afecta qué botones y vistas renderiza el frontend (Angular), pero la verdadera seguridad del acceso a los archivos la dictamina el backend validando la firma del `authToken`.
#### Referencias
- [JWT.io - Decodificador y generador de tokens JWT](https://jwt.io/)
- [Vulnerabilidades comunes en implementaciones JWT (OWASP)](https://cheatsheetseries.owasp.org/cheatsheets/JSON_Web_Token_for_Java_Cheat_Sheet.html)
