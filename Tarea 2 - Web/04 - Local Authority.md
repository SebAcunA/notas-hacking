#### Descripción 
Can you get the flag?Go to this [website](http://saturn.picoctf.net:58015/) and see what you can discover.
#### Solución
```
function checkPassword(username, password)
{
  if( username === 'admin' && password === 'strongPassword098765' )
  {
    return true;
  }
  else
  {
    return false;
  }
}
```
#### Notas
Revisando los archivos del programa al momento de manipular apareció un secure.js
#### Referencias