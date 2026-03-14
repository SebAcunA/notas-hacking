#### Descripción 
I stopped using YellowPages and moved onto WhitePages... but [the page they gave me](https://challenge-files.picoctf.net/c_fickle_tempest/4de4b105d28cb6df34d9805217f2460b978a37dafc3dfc50edadd8d424dd311a/whitepages.txt) is all blank!
#### Solución
```
┌──(venv)─(kali㉿kali)-[~/forensic]
└─$ python exp.py
Traceback (most recent call last):
  File "/home/kali/forensic/exp.py", line 3, in <module>
    file = open('whiteepages.txt', 'rb')
FileNotFoundError: [Errno 2] No such file or directory: 'whiteepages.txt'
                                                                                                                    
┌──(venv)─(kali㉿kali)-[~/forensic]
└─$ dir
exp.py  message.wav  result.png  sstv  whitepages.txt
                                                                                                                    
┌──(venv)─(kali㉿kali)-[~/forensic]
└─$ nano exp.py  
                                                                                                                    
┌──(venv)─(kali㉿kali)-[~/forensic]
└─$ python exp.py
b'\npicoCTF\n\nSEE PUBLIC RECORDS & BACKGROUND REPORT\n5000 Forbes Ave, Pittsburgh, PA 15213\npicoCTF{not_all_spaces_are_created_equal_f5d46aff52c6e17f9fd6317b33d2d783}\n'
                                                                                                                    
┌──(venv)─(kali㉿kali)-[~/forensic]
└─$ 

```
#### Notas
#### Referencias

