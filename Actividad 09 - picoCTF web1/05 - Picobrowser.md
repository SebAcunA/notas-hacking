#### Descripción 
This website can be rendered only by picobrowser, go and catch the flag!
http://fickle-tempest.picoctf.net:59081
#### Solución
```
SebAcuna-picoctf@webshell:~$ curl -s http://fickle-tempest.picoctf.net:59081/flag -H "User-Agent: picobrowser" | grep picoCTF
            <p style="text-align:center; font-size:30px;"><b>Flag</b>: <code>picoCTF{p1c0_s3cr3t_ag3nt_fba5c48f}</code></p>
SebAcuna-picoctf@webshell:~$ 

```
#### Notas
#### Referencias
