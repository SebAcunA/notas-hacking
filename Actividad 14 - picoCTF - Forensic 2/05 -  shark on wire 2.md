#### Descripción 
We found this [packet capture](https://challenge-files.picoctf.net/c_fickle_tempest/ca7e8f9bb6b060dd724f90e3243aa3e36fc0d98c9b421cef0e860d1ff75f9ef0/capture.pcap). Recover the flag.
#### Solución
```
  GNU nano 8.6                                           exp.py *                                                   
from scapy.all import *

packets = rdpcap('capture.pcap')

flag = ''

for p in packets:
        if UDP in p and p[UDP].dport == 22:
                if p[UDP].sport > 5000:
                        flag += chr(p[UDP].sport - 5000)

print(flag)



┌──(kali㉿kali)-[~/forensic]
└─$ mkdir sharkonwire2; cd sharkonwire2
                                                                                                                    
┌──(kali㉿kali)-[~/forensic/sharkonwire2]
└─$ wget https://challenge-files.picoctf.net/c_fickle_tempest/ca7e8f9bb6b060dd724f90e3243aa3e36fc0d98c9b421cef0e860d1ff75f9ef0/capture.pcap
--2026-03-13 21:06:44--  https://challenge-files.picoctf.net/c_fickle_tempest/ca7e8f9bb6b060dd724f90e3243aa3e36fc0d98c9b421cef0e860d1ff75f9ef0/capture.pcap
Resolving challenge-files.picoctf.net (challenge-files.picoctf.net)... 18.238.132.49, 18.238.132.88, 18.238.132.26, ...
Connecting to challenge-files.picoctf.net (challenge-files.picoctf.net)|18.238.132.49|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 112318 (110K) [application/octet-stream]
Saving to: ‘capture.pcap’

capture.pcap                 100%[==============================================>] 109.69K  --.-KB/s    in 0.08s   

2026-03-13 21:06:45 (1.36 MB/s) - ‘capture.pcap’ saved [112318/112318]

                                                                                                                    
┌──(kali㉿kali)-[~/forensic/sharkonwire2]
└─$ dir
capture.pcap
                                                                                                                    
┌──(kali㉿kali)-[~/forensic/sharkonwire2]
└─$ python3 -m pip install scapy
error: externally-managed-environment

× This environment is externally managed
╰─> To install Python packages system-wide, try apt install
    python3-xyz, where xyz is the package you are trying to
    install.
    
    If you wish to install a non-Kali-packaged Python package,
                                                                                                                    
┌──(kali㉿kali)-[~/forensic/sharkonwire2]
└─$ nano exp.py                   
                                                                                                                    
┌──(kali㉿kali)-[~/forensic/sharkonwire2]
└─$ python3 exp.py                
Traceback (most recent call last):
  File "/home/kali/forensic/sharkonwire2/exp.py", line 3, in <module>
    packets = rdcap('capture.pcap')
              ^^^^^
NameError: name 'rdcap' is not defined
                                                                                                                    
┌──(kali㉿kali)-[~/forensic/sharkonwire2]
└─$ nano exp.py    
                                                                                                                    
┌──(kali㉿kali)-[~/forensic/sharkonwire2]
└─$ python3 exp.py 
picoCTF{p1LLf3r3d_data_v1a_st3g0}
```
#### Notas
#### Referencias
