#### Descripción 
The Multiverse is within your grasp! Unfortunately, the server that contains the secrets of the multiverse is in a universe where keyboards only have numbers and (most) symbols.

`ssh -p 60411 ctf-player@mimas.picoctf.net`

Use password: `6dd28e9b`
#### Solución
``` 
rosyperez@MacBookAir src % ssh -p 60411 ctf-player@mimas.picoctf.net
The authenticity of host '[mimas.picoctf.net]:60411 ([52.15.88.75]:60411)' can't be established.
ED25519 key fingerprint is SHA256:n/hDgUtuTTF85Id7k2fxmHvb6rrLrACHNM6xLZ46AqQ.
This key is not known by any other names.
Are you sure you want to continue connecting (yes/no/[fingerprint])? yes
Warning: Permanently added '[mimas.picoctf.net]:60411' (ED25519) to the list of known hosts.
ctf-player@mimas.picoctf.net's password: 
Permission denied, please try again.
ctf-player@mimas.picoctf.net's password: 
Welcome to Ubuntu 20.04.3 LTS (GNU/Linux 6.8.0-1053-aws x86_64
 * Documentation:  https://help.ubuntu.com
 * Management:     https://landscape.canonical.com
 * Support:        https://ubuntu.com/advantage
This system has been minimized by removing packages and content that are
not required on a system that users do not log into.  
To restore this content, you can run the 'unminimize' command.  
The programs included with the Ubuntu system are free software;
the exact distribution terms for each program are described in the
individual files in /usr/share/doc/*/copyright.  
Ubuntu comes with ABSOLUTELY NO WARRANTY, to the extent permitted by
applicable law.  
SansAlpha$ ls
SansAlpha: Unknown character detected
SansAlpha$ {_1:0:11} ??????/????.???
bash: {_1:0:11}: command not found
SansAlpha$ ${_1:0:11} ??????/????.???
bash: blargh/flag.txt: Permission denied  
SansAlpha$ 1=`/???/????32 2>&1`
bash: 1=/bin/base32:: No such file or directory 
SansAlpha$ _1=`/???/????32 2>&1`
SansAlpha$ ${_1:0:11} ??????/????.???
OJSXI5LSNYQDAIDQNFRW6Q2UIZ5TO2BRGVPW25JRG4YXMM3SGUZV6MJVL5WTIZDOGM2TKXZRGQ2T
ENJWMVRX2===
SansAlpha$
```
#### Notas
El reto consistía en interactuar con una shell restringida llamada `SansAlpha`, la cual bloqueaba el uso de letras directamente desde el teclado. Para evadir esta limitación se utilizaron comodines (`?`) y expansión de variables de Bash para ejecutar comandos sin escribir caracteres alfabéticos manualmente. Primero se obtuvo la ruta de `/bin/base32` mediante sustitución de comandos y posteriormente se ejecutó sobre el archivo `blargh/flag.txt`, obteniendo una salida codificada en Base32. Finalmente, el resultado fue decodificado utilizando CyberChef para recuperar la flag.
#### Referencias
https://gchq.github.io/CyberChef/#recipe=From_Base32('A-Z2-7%3D',false)&input=T0pTWEk1TFNOWVFEQUlEUU5GUlc2UTJVSVo1VE8yQlJHVlBXMjVKUkc0WVhNTTNTR1VaVjZNSlZMNVdUSVpET0dNMlRLWFpSR1EyVEVOSldNVlJYMj09PQ&oeol=FF