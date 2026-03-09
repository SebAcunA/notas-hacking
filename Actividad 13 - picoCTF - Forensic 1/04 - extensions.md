#### Descripción 
This is a really weird text file. Can you find the flag?Get the flag from [TXT](https://challenge-files.picoctf.net/c_fickle_tempest/31fe772e6a4c71e867af0b2a93818e06d8f8ebf8af2a9615495d00356ff576da/flag.txt).
#### Solución
```
┌──(kali㉿kali)-[~/picoctf/forensinc/04]
└─$ wget https://challenge-files.picoctf.net/c_fickle_tempest/134d2a2cf6ec5b7e757effc9b32977af7cc324b8e99a5ddb64737794a14dc18d/capture.pcap
--2026-03-09 10:46:00--  https://challenge-files.picoctf.net/c_fickle_tempest/134d2a2cf6ec5b7e757effc9b32977af7cc324b8e99a5ddb64737794a14dc18d/capture.pcap
Resolving challenge-files.picoctf.net (challenge-files.picoctf.net)... 18.154.206.121, 18.154.206.14, 18.154.206.27, ...
Connecting to challenge-files.picoctf.net (challenge-files.picoctf.net)|18.154.206.121|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 239455 (234K) [application/octet-stream]
Saving to: ‘capture.pcap’

capture.pcap        100%[================>] 233.84K   452KB/s    in 0.5s    

2026-03-09 10:46:07 (452 KB/s) - ‘capture.pcap’ saved [239455/239455]

┌──(kali㉿kali)-[~/picoctf/forensinc/04]
└─$ xxd -l 20 flag.txt
00000000: 8950 4e47 0d0a 1a0a 0000 000d 4948 4452  .PNG........IHDR
00000010: 0000 06a1 

┌──(kali㉿kali)-[~/picoctf/forensinc/04]
└─$ mv flag.txt flag.png
                                                                             
┌──(kali㉿kali)-[~/picoctf/forensinc/04]
└─$ xdg-open flag.png

```
#### Notas
Observar el contenido para saber si se trata de una extensión oculta 
#### Referencias