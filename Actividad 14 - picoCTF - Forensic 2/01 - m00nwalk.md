#### Descripción 
Decode this [message](https://challenge-files.picoctf.net/c_fickle_tempest/678ff56c639c7645276578f3a9767ec2feaed1450045dd982c525b5795f7f589/message.wav) from the moon.
#### Solución
```
┌──(kali㉿kali)-[~/forensic/sstv]
└─$ sstv                         
┌──(kali㉿kali)-[~/forensic/sstv/sstv]
└─$ cd ..                                                                          
┌──(kali㉿kali)-[~/forensic/sstv]
└─$ cd ..                                                                          
┌──(kali㉿kali)-[~/forensic]
└─$ wget https://challenge-files.picoctf.net/c_fickle_tempest/678ff56c639c7645276578f3a9767ec2feaed1450045dd982c525b5795f7f589/message.wav 
--2026-03-12 04:46:19--  https://challenge-files.picoctf.net/c_fickle_tempest/678ff56c639c7645276578f3a9767ec2feaed1450045dd982c525b5795f7f589/message.wav
Resolving challenge-files.picoctf.net (challenge-files.picoctf.net)... 3.161.44.22, 3.161.44.61, 3.161.44.84, ...
Connecting to challenge-files.picoctf.net (challenge-files.picoctf.net)|3.161.44.22|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 11066998 (11M) [application/octet-stream]
Saving to: ‘message.wav’

message.wav                                                100%[========================================================================================================================================>]  10.55M  12.7MB/s    in 0.8s    

2026-03-12 04:46:26 (12.7 MB/s) - ‘message.wav’ saved [11066998/11066998]

                                                                                                                                                                                                                                            
┌──(kali㉿kali)-[~/forensic]
└─$ sstv -d message.wav -o result.png
[sstv] Searching for calibration header... Found!    
[sstv] Detected SSTV mode Scottie 1
[sstv] Decoding image...                                                                                                         [####################################################################################################] 100%
[sstv] Drawing image data...
[sstv] ...Done!

```
#### Notas
La imagen venia al reves y usamos la herramienta del visor de kali para poder visualizarla y anotarla manual
#### Referencias
