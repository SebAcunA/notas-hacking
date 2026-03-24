#### Descripción 
Use `srch_strings` from the sleuthkit and some terminal-fu to find a flag in this disk image.
[dds1-alpine.flag.img.gz](https://challenge-files.picoctf.net/c_wily_courier/27cbd6a2ed4a59d600f2a24c1ccaa6de66f9aeee95d6b365160fd75649e45f1b/dds1-alpine.flag.img.gz)

#### Solución
```

2026-03-23 10:12:05 (4.16 MB/s) - ‘dds1-alpine.flag.img.gz’ saved [29768911/29768911]

                                                                                                                    
┌──(kali㉿kali)-[~/forensic/sleudth]
└─$ srch string dds1-alpine.flag.img | grep pico
Command 'srch' not found, did you mean:
  command 'src' from deb simple-revision-control
  command 'arch' from deb coreutils
Try: sudo apt install <deb name>
                                                                                                                    
┌──(kali㉿kali)-[~/forensic/sleudth]
└─$ srch_string dds1-alpine.flag.img | grep pico
Command 'srch_string' not found, did you mean:
  command 'srch_strings' from deb sleuthkit
Try: sudo apt install <deb name>
                                                                                                                    
┌──(kali㉿kali)-[~/forensic/sleudth]
└─$ sudo apt install sleuthkit                 
sleuthkit is already the newest version (4.12.1+dfsg-0kali6).
Summary:                    
  Upgrading: 0, Installing: 0, Removing: 0, Not Upgrading: 0
                                                                                                                    
┌──(kali㉿kali)-[~/forensic/sleudth]
└─$ srch_string dds1-alpine.flag.img | grep pico
Command 'srch_string' not found, did you mean:
  command 'srch_strings' from deb sleuthkit
Try: sudo apt install <deb name>
                                                                                                                    
┌──(kali㉿kali)-[~/forensic/sleudth]
└─$ 
                                                                                                                    
┌──(kali㉿kali)-[~/forensic/sleudth]
└─$ srch_strings dds1-alpine.flag.img | grep pico        
'dds1-alpine.flag.img': No such file
                                                                                                                    
┌──(kali㉿kali)-[~/forensic/sleudth]
└─$ gzip -d dds1-alpine.flag.img.gz                 
                                                                                                                    
┌──(kali㉿kali)-[~/forensic/sleudth]
└─$ dir
dds1-alpine.flag.img
                                                                                                                    
┌──(kali㉿kali)-[~/forensic/sleudth]
└─$ srch_strings dds1-alpine.flag.img | grep pico
ffffffff81399ccf t pirq_pico_get
ffffffff81399cee t pirq_pico_set
ffffffff820adb46 t pico_router_probe
  SAY picoCTF{f0r3ns1c4t0r_n30phyt3_5e56e786}
                                                
```
#### Notas
#### Referencias