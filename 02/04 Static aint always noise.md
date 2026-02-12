#### Descripción 
Can you look at the data in this binary? The bash script might help![static](https://challenge-files.picoctf.net/c_wily_courier/b06384f5fdb3a6e3f0f254d1064d203e7df4bf7e9a5780a95622523367d82bc0/static), [ltdis.sh](https://challenge-files.picoctf.net/c_wily_courier/b06384f5fdb3a6e3f0f254d1064d203e7df4bf7e9a5780a95622523367d82bc0/ltdis.sh)
#### Solución
```
SebAcuna-picoctf@webshell:~$ chmod +x ltdis.sh
SebAcuna-picoctf@webshell:~$ ./ltdis.sh static
Attempting disassembly of static ...
Disassembly successful! Available at: static.ltdis.x86_64.txt
Ripping strings from binary with file offsets...
Any strings found in static have been written to static.ltdis.strings.txt with file offset
SebAcuna-picoctf@webshell:~$ strings static | grep pico 
picoCTF{d15a5m_t34s3r_20335e41}
```
#### Notas
#### Referencias
