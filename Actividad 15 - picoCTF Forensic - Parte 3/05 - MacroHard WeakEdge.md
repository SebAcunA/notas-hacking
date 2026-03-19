#### Descripción 
I've hidden a flag in this file. Can you find it?
[Forensics_is_fun.pptm](https://challenge-files.picoctf.net/c_wily_courier/d78815176c19ddc85a1388233268d2f4c459fcbbaab197b4a29ebafc88294c54/Forensics_is_fun.pptm)
#### Solución
```
  inflating: ppt/slideMasters/hidden  
                                                                                                     
┌──(kali㉿kali)-[~/forensic/MacroHard]
└─$ cd ppt/slideMasters 
                                                                                                     
┌──(kali㉿kali)-[~/forensic/MacroHard/ppt/slideMasters]
└─$ ls
hidden  _rels  slideMaster1.xml
                                                                                                     
┌──(kali㉿kali)-[~/forensic/MacroHard/ppt/slideMasters]
└─$ cat hidden         
Z m x h Z z o g c G l j b 0 N U R n t E M W R f d V 9 r b j B 3 X 3 B w d H N f c l 9 6 M X A 1 f Q                                                                                                     
┌──(kali㉿kali)-[~/forensic/MacroHard/ppt/slideMasters]
└─$ echo "Z m x h Z z o g c G l j b 0 N U R n t E M W R f d V 9 r b j B 3 X 3 B w d H N f c l 9 6 M X A 1 f Q" | tr -d " " | base64 -d
flag: [[picoCTF{D1d_u_kn0w_ppts_r_z1p5}]]
```
#### Notas
#### Referencias

