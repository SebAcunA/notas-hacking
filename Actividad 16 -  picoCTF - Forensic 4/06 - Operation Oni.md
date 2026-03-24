#### Descripción 
Download this disk image, find the key and log into the remote machine.Note: if you are using the webshell, download and extract the disk image into `/tmp` not your home directory.

Additional details will be available after launching your challenge instance.
#### Solución
```
┌──(kali㉿kali)-[~/forensic]
└─$ mkdir OperationOni   
                                                                                                                    
┌──(kali㉿kali)-[~/forensic]
└─$ cd OperationOni   
                                                                                                                    
┌──(kali㉿kali)-[~/forensic/OperationOni]
└─$ wget https://artifacts.picoctf.net/c/70/disk.img.gz      
--2026-03-23 10:54:47--  https://artifacts.picoctf.net/c/70/disk.img.gz
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 3.161.55.64, 3.161.55.26, 3.161.55.61, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|3.161.55.64|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 48132743 (46M) [application/octet-stream]
Saving to: ‘disk.img.gz’

disk.img.gz                  100%[==============================================>]  45.90M  5.49MB/s    in 8.1s    

2026-03-23 10:55:14 (5.64 MB/s) - ‘disk.img.gz’ saved [48132743/48132743]

                                                                                                                    
┌──(kali㉿kali)-[~/forensic/OperationOni]
└─$ gzip -d disk.img.gz     

                                                                                                                    
┌──(kali㉿kali)-[~/forensic/OperationOni]
└─$ 
                                                                                                                    
┌──(kali㉿kali)-[~/forensic/OperationOni]
└─$ mmls              
Missing image name
usage: mmls [-i imgtype] [-b dev_sector_size] [-o imgoffset] [-BrvV] [-aAmM] [-t vstype] image [images]
        -t vstype: The type of volume system (use '-t list' for list of supported types)
        -i imgtype: The format of the image file (use '-i list' for list supported types)
        -b dev_sector_size: The size (in bytes) of the device sectors
        -o imgoffset: Offset to the start of the volume that contains the partition system (in sectors)
        -B: print the rounded length in bytes
        -r: recurse and look for other partition tables in partitions (DOS Only)
        -v: verbose output
        -V: print the version
Unless any of these are specified, all volume types are shown
        -a: Show allocated volumes
        -A: Show unallocated volumes
        -m: Show metadata volumes
        -M: Hide metadata volumes
                                                                                                                    
┌──(kali㉿kali)-[~/forensic/OperationOni]
└─$ mmls disk.img     
DOS Partition Table
Offset Sector: 0
Units are in 512-byte sectors

      Slot      Start        End          Length       Description
000:  Meta      0000000000   0000000000   0000000001   Primary Table (#0)
001:  -------   0000000000   0000002047   0000002048   Unallocated
002:  000:000   0000002048   0000206847   0000204800   Linux (0x83)
003:  000:001   0000206848   0000471039   0000264192   Linux (0x83)
                                                                                                                    
┌──(kali㉿kali)-[~/forensic/OperationOni]
└─$ fls -o 206848 disk.img            
d/d 458:        home
d/d 11: lost+found
d/d 12: boot
d/d 13: etc
d/d 79: proc
d/d 80: dev
d/d 81: tmp
d/d 82: lib
d/d 85: var
d/d 94: usr
d/d 104:        bin
d/d 118:        sbin
d/d 464:        media
d/d 468:        mnt
d/d 469:        opt
d/d 470:        root
d/d 471:        run
d/d 473:        srv
d/d 474:        sys
V/V 33049:      $OrphanFiles
                                                                                                                    
┌──(kali㉿kali)-[~/forensic/OperationOni]
└─$ fls -o 206848 disk.img 470
r/r 2344:       .ash_history
d/d 3916:       .ssh
                                                                                                                    
┌──(kali㉿kali)-[~/forensic/OperationOni]
└─$ fls -o 206848 disk.img 470 -r
r/r 2344:       .ash_history
d/d 3916:       .ssh
+ r/r 2345:     id_ed25519
+ r/r 2346:     id_ed25519.pub
                                                                                                                    
┌──(kali㉿kali)-[~/forensic/OperationOni]
└─$ icat -o 206848 disk.img 2345 > key_file
                                                                                                                    
┌──(kali㉿kali)-[~/forensic/OperationOni]
└─$ file key_file                
key_file: OpenSSH private key
                                                                                                                    
┌──(kali㉿kali)-[~/forensic/OperationOni]
└─$ chmod 600 key_file
                                                                                                                    
┌──(kali㉿kali)-[~/forensic/OperationOni]
└─$ ssh -i key_file -p 49249 ctf-player@saturn.picoctf.net
The authenticity of host '[saturn.picoctf.net]:49249 ([13.59.203.175]:49249)' can't be established.
ED25519 key fingerprint is: SHA256:XBSvB1lk28EctsAVdKJtsl0A7C5bonqPrvHCYH8aEy4
This key is not known by any other names.
Are you sure you want to continue connecting (yes/no/[fingerprint])? yes
Warning: Permanently added '[saturn.picoctf.net]:49249' (ED25519) to the list of known hosts.
** WARNING: connection is not using a post-quantum key exchange algorithm.
** This session may be vulnerable to "store now, decrypt later" attacks.
** The server may need to be upgraded. See https://openssh.com/pq.html
Welcome to Ubuntu 20.04.5 LTS (GNU/Linux 6.8.0-1047-aws x86_64)

 * Documentation:  https://help.ubuntu.com
 * Management:     https://landscape.canonical.com
 * Support:        https://ubuntu.com/advantage

This system has been minimized by removing packages and content that are
not required on a system that users do not log into.

To restore this content, you can run the 'unminimize' command.

The programs included with the Ubuntu system are free software;
the exact distribution terms for each program are described in the
individual files in /usr/share/doc/*/copyright.

Ubuntu comes with ABSOLUTELY NO WARRANTY, to the extent permitted by
applicable law.

ctf-player@challenge:~$ ls
flag.txt
ctf-player@challenge:~$ cat flag.txt
picoCTF{k3y_5l3u7h_b5066e83}ctf-player@challenge:~$ Connection to saturn.picoctf.net closed by remote host.
Connection to saturn.picoctf.net closed.

```
#### Notas
#### Referencias
