#### Descripción 
I've gotten bored of handing out flags as text. Wouldn't it be cool if they were an image instead?You can download the challenge files here:

- [challenge.zip](https://artifacts.picoctf.net/c_atlas/13/challenge.zip)

The same files are accessible via SSH here:`ssh -p 58545 ctf-player@atlas.picoctf.net`Using the password `f3b61b38`. Accept the fingerprint with `yes`, and `ls` once connected to begin. Remember, in a shell, passwords are hidden!
#### Solución
```
┌──(kali㉿kali)-[~/forensic]
└─$ mkdir ScanSurprise; cd ScanSurprise
                                                                                                                                                                                                                                            
┌──(kali㉿kali)-[~/forensic/ScanSurprise]
└─$ ls
                                                                                                                                                                                                                                            
┌──(kali㉿kali)-[~/forensic/ScanSurprise]
└─$ ssh -p 58545 ctf-player@atlas.picoctf.net        
The authenticity of host '[atlas.picoctf.net]:58545 ([18.217.83.136]:58545)' can't be established.
ED25519 key fingerprint is: SHA256:hVmbk/OaNT4902bBr7h26wfhmBuJWi4tub8AJqoAJCM
This key is not known by any other names.
Are you sure you want to continue connecting (yes/no/[fingerprint])? yes
Warning: Permanently added '[atlas.picoctf.net]:58545' (ED25519) to the list of known hosts.
** WARNING: connection is not using a post-quantum key exchange algorithm.
** This session may be vulnerable to "store now, decrypt later" attacks.
** The server may need to be upgraded. See https://openssh.com/pq.html
ctf-player@atlas.picoctf.net's password: 
IMAGEN DE CÓDGO QR AQUÍ    
ctf-player@challenge:~/drop-in$ ls
flag.png
ctf-player@challenge:~/drop-in$ xdg-open flag.png
rbash: xdg-open: command not found
ctf-player@challenge:~/drop-in$ 

Escaneando con el celular en la barra de busqueda me aparecio este texto
picoCTF{p33k_@_b00_d4ca652e}
```
#### Notas
este reto fue bastante curioso porque implementó el uso de el celular, pareciera que el reto salió de la computadora a modificar nuestro entorno en la vida real
#### Referencias
