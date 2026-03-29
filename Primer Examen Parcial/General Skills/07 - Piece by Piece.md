#### Descripción 
After logging in, you will find multiple file parts in your home directory. These parts need to be combined and extracted to reveal the flag.
SSH to `dolphin-cove.picoctf.net`:`53216` and login as `ctf-player` with password `a15d25e1`.
#### Solución
```
SebAcuna-picoctf@webshell:~$ ssh -p 52066 ctf-player@dolphin-cove.picoctf.net
The authenticity of host '[dolphin-cove.picoctf.net]:52066 ([3.13.34.175]:52066)' can't be established.
ED25519 key fingerprint is SHA256:rdvWhF7Klwlu1EivysxTh/FjeqFI0dSEK5gaelaW9t8.
This host key is known by the following other names/addresses:
    ~/.ssh/known_hosts:9: [hashed name]
Are you sure you want to continue connecting (yes/no/[fingerprint])? yes
Warning: Permanently added '[dolphin-cove.picoctf.net]:52066' (ED25519) to the list of known hosts.
ctf-player@dolphin-cove.picoctf.net's password: 
Welcome to Ubuntu 20.04.3 LTS (GNU/Linux 6.17.0-1009-aws x86_64)

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

ctf-player@pico-chall$ dir
instructions.txt  part_aa  part_ab  part_ac  part_ad  part_ae
ctf-player@pico-chall$ cat instructions.txt
Hint:

- The flag is split into multiple parts as a zipped file.
- Use Linux commands to combine the parts into one file.
- The zip file is password protected. Use this "supersecret" password to extract the zip file.
- After unzipping, check the extracted text file for the flag.


ctf-player@pico-chall$ cat part_* > flag.zip
ctf-player@pico-chall$ file flag.zip
flag.zip: Zip archive data, at least v1.0 to extract
ctf-player@pico-chall$ unzip -P supersecret flag.zip
Archive:  flag.zip
 extracting: flag.txt                
ctf-player@pico-chall$ unzip -P supersecret flag.zip
Archive:  flag.zip
replace flag.txt? [y]es, [n]o, [A]ll, [N]one, [r]ename: y
 extracting: flag.txt                
ctf-player@pico-chall$ ls
flag.txt  flag.zip  instructions.txt  part_aa  part_ab  part_ac  part_ad  part_ae
ctf-player@pico-chall$ cat flag.txt
picoCTF{z1p_and_spl1t_f1l3s_4r3_fun_da494d2e}
```
#### Notas
#### Referencias