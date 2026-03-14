#### Descripción 
We found this [file](https://challenge-files.picoctf.net/c_fickle_tempest/87bdc8ce30b177d033b3d68bca4647950bb07304032861baa912ebe08701d355/mystery). Recover the flag.
#### Solución
```
┌──(kali㉿kali)-[~/forensic]
└─$ file c0rrupt
c0rrupt: directory
                                                                                                                    
┌──(kali㉿kali)-[~/forensic]
└─$ cd c0rrupt 
                                                                                                                    
┌──(kali㉿kali)-[~/forensic/c0rrupt]
└─$ dir
mystery
                                                                                                                    
┌──(kali㉿kali)-[~/forensic/c0rrupt]
└─$ file mystery
mystery: data
                                                                                                                    
┌──(kali㉿kali)-[~/forensic/c0rrupt]
└─$ hexedit mystery
Command 'hexedit' not found, but can be installed with:
sudo apt install hexedit
Do you want to install it? (N/y)y
sudo apt install hexedit
[sudo] password for kali: 
Error: Unable to locate package hexedit
                                                                                                                    
┌──(kali㉿kali)-[~/forensic/c0rrupt]
└─$ hexeditor mystery
                                                                                                                    
┌──(kali㉿kali)-[~/forensic/c0rrupt]
└─$ sudo apt install pngcheck
.... -- muchos comandos
                                                                                                                    
┌──(kali㉿kali)-[~/forensic/c0rrupt]
└─$ pngcheck -v mystery
File: mystery (209190 bytes)
chunk IHDR at offset 0x0000c, Length 13
  1642 x 1095 image, 24-bit RGB, non-interlaced
chunk sRGB at offset 0x00025, Length 1
  rendering intent = perceptual
chunk gAMA at offset 0x00032, Length 4: 0.45455
chunk pHYs at offset 0x00042, Length 9: 5669x5669 pixels/meter (144 dpi)
chunk IDAT at offset 0x00057, Length 65545
  zlib: Deflated, 32K window, fast compression
chunk IDAT at offset 0x10008, Length 65524
chunk IDAT at offset 0x20038, Length 684
chunk IEND at offset 0x301b4, Length 0
No errors detected in mystery (9 chunks, 96.3% compression).        
                                                                            
┌──(kali㉿kali)-[~/forensic/c0rrupt]
└─$ open mystery

```
#### Notas

#### Referencias
