#### Descripción 
How about trying to match a regular expressionThe website is running [here](http://saturn.picoctf.net:50133/).
#### Solución
```
	function send_request() {
		let val = document.getElementById("name").value;
		// ^p.....F!?
		fetch(`/flag?input=${val}`)
			.then(res => res.text())
			.then(res => {
				const res_json = JSON.parse(res);
				alert(res_json.flag)
				return false;
			})
		return false;
	}
```
#### Notas
"^" significa incio de una cadena regular 
por ejemplo:
- `^hola` → coincide con cualquier texto que **empiece** con “hola” (ej. “hola mundo”).
- `^p.....F` → coincide con cualquier texto que **empiece con “p”**, tenga 5 caracteres cualquiera, y luego una “F”.
- No tiene algo que indique el cierre de la cadena con el símbolo`$`por lo tanto podemos poner los caracteres que queramos después de F para 
#### Referencias
https://www.youtube.com/watch?v=YZemkSTN50U&list=PLDo9DMLZyP6kTZ8Td37-LdbAx4-yNfHBl&index=64
