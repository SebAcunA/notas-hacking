#### Descripción 
Download this disk image and find the flag.Note: if you are using the webshell, download and extract the disk image into `/tmp` not your home directory.

- [Download compressed disk image](https://artifacts.picoctf.net/c/213/disk.flag.img.gz)
#### Solución
```
┌──(kali㉿kali)-[~/forensic/OperationOrchid]
└─$ ls -l
total 43324
-rw-rw-r-- 1 kali kali 44360922 Mar 15  2023 disk.flag.img.gz
                                                                                                                    
┌──(kali㉿kali)-[~/forensic/OperationOrchid]
└─$ gzip -d disk.flag.img.gz
                                                                                                                    
┌──(kali㉿kali)-[~/forensic/OperationOrchid]
└─$ mmls disk.flag.img                                    
DOS Partition Table
Offset Sector: 0
Units are in 512-byte sectors

      Slot      Start        End          Length       Description
000:  Meta      0000000000   0000000000   0000000001   Primary Table (#0)
001:  -------   0000000000   0000002047   0000002048   Unallocated
002:  000:000   0000002048   0000206847   0000204800   Linux (0x83)
003:  000:001   0000206848   0000411647   0000204800   Linux Swap / Solaris x86 (0x82)
004:  000:002   0000411648   0000819199   0000407552   Linux (0x83)
                                                                                                                    
┌──(kali㉿kali)-[~/forensic/OperationOrchid]
└─$ fls -o 411648 disk.flag.img         
d/d 460:        home
d/d 11: lost+found
d/d 12: boot
d/d 13: etc
d/d 81: proc
d/d 82: dev
d/d 83: tmp
d/d 84: lib
d/d 87: var
d/d 96: usr
d/d 106:        bin
d/d 120:        sbin
d/d 466:        media
d/d 470:        mnt
d/d 471:        opt
d/d 472:        root
d/d 473:        run
d/d 475:        srv
d/d 476:        sys
d/d 2041:       swap
V/V 51001:      $OrphanFiles
                                                                                                                    
┌──(kali㉿kali)-[~/forensic/OperationOrchid]
└─$ fls -o 411648 disk.flag.img 472 -r
r/r 1875:       .ash_history
r/r * 1876(realloc):    flag.txt
r/r 1782:       flag.txt.enc
                                                                                                                    
┌──(kali㉿kali)-[~/forensic/OperationOrchid]
└─$ icat -o 411648 disk.flag.img 1876  
           -0.881573            34.311733
                                                                                                                    
┌──(kali㉿kali)-[~/forensic/OperationOrchid]
└─$ icat -o 411648 disk.flag.img 1782
Salted__�ށ��e��B�J▒�c�$QE&$��4jM�KGeE�1�^Ȥ7� ���؎$�'%                                                                                                                    
┌──(kali㉿kali)-[~/forensic/OperationOrchid]
└─$ icat -o 411648 disk.flag.img 1875
touch flag.txt
nano flag.txt 
apk get nano
apk --help
apk add nano
nano flag.txt 
openssl
openssl aes256 -salt -in flag.txt -out flag.txt.enc -k unbreakablepassword1234567
shred -u flag.txt
ls -al
halt
                                                                                                                    
┌──(kali㉿kali)-[~/forensic/OperationOrchid]
└─$ fls -o 411648 disk.flag.img       
d/d 460:        home
d/d 11: lost+found
d/d 12: boot
d/d 13: etc
d/d 81: proc
d/d 82: dev
d/d 83: tmp
d/d 84: lib
d/d 87: var
d/d 96: usr
d/d 106:        bin
d/d 120:        sbin
d/d 466:        media
d/d 470:        mnt
d/d 471:        opt
d/d 472:        root
d/d 473:        run
d/d 475:        srv
d/d 476:        sys
d/d 2041:       swap
V/V 51001:      $OrphanFiles
                                                                                                                    
┌──(kali㉿kali)-[~/forensic/OperationOrchid]
└─$ fls -o 411648 disk.flag.img 472 -r
r/r 1875:       .ash_history
r/r * 1876(realloc):    flag.txt
r/r 1782:       flag.txt.enc
                                                                                                                    
┌──(kali㉿kali)-[~/forensic/OperationOrchid]
└─$ icat -p 411648 disk.flag.img 1782 > flag.txt.enc
icat: invalid option -- 'p'
Invalid argument: 411648
usage: icat [-hrRsvV] [-f fstype] [-i imgtype] [-b dev_sector_size] [-o imgoffset] image [images] inum[-typ[-id]]
        -h: Do not display holes in sparse files
        -r: Recover deleted file
        -R: Recover deleted file and suppress recovery errors
        -s: Display slack space at end of file
        -i imgtype: The format of the image file (use '-i list' for supported types)
        -b dev_sector_size: The size (in bytes) of the device sectors
        -f fstype: File system type (use '-f list' for supported types)
        -o imgoffset: The offset of the file system in the image (in sectors)
        -P pooltype: Pool container type (use '-P list' for supported types)
        -B pool_volume_block: Starting block (for pool volumes only)
        -S snap_id: Snapshot ID (for APFS only)
        -v: verbose to stderr
        -V: Print version
        -k password: Decryption password for encrypted volumes
                                                                                                                    
┌──(kali㉿kali)-[~/forensic/OperationOrchid]
└─$ icat -o 411648 disk.flag.img 1782 > flag.txt.enc
                                                                                                                    
┌──(kali㉿kali)-[~/forensic/OperationOrchid]
└─$ openssl aes256 -salt -d -in flag.txt.enc -out flag.txt -k unbreakablepassword1234567 
*** WARNING : deprecated key derivation used.
Using -iter or -pbkdf2 would be better.
bad decrypt
40873110FC7E0000:error:1C800064:Provider routines:ossl_cipher_unpadblock:bad decrypt:../providers/implementations/ciphers/ciphercommon_block.c:107:
                                                                                                                    
┌──(kali㉿kali)-[~/forensic/OperationOrchid]
└─$ dir
disk.flag.img  flag.txt  flag.txt.enc
                                                                                                                    
┌──(kali㉿kali)-[~/forensic/OperationOrchid]
└─$ cat flag.txt      
picoCTF{h4un71ng_p457_5113beab}
```
#### Notas
#### Referencias
