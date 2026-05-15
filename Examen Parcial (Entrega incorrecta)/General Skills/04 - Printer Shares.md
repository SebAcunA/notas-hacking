#### Descripción 
Oops! Someone accidentally sent an important file to a network printer—can you retrieve it from the print server?The printer is on `49787`.
you can try 
`$ nc -vz mysterious-sea.picoctf.net 49787`
#### Solución
```
SebAcuna-picoctf@webshell:~$ nc -vz mysterious-sea.picoctf.net 49787`
> ls
> dir
> 
> 
> ^C
SebAcuna-picoctf@webshell:~$ smbclient -N //mysterious-sea.picoctf.net/print$ -p 49787
tree connect failed: NT_STATUS_BAD_NETWORK_NAME
SebAcuna-picoctf@webshell:~$ smbclient -L mysterious-sea.picoctf.net -p 49787 -N

        Sharename       Type      Comment
        ---------       ----      -------
        shares          Disk      Public Share With Guests
        IPC$            IPC       IPC Service (Samba 4.19.5-Ubuntu)
SMB1 disabled -- no workgroup available
SebAcuna-picoctf@webshell:~$ smbclient //mysterious-sea.picoctf.net/shares -p 49787 -N
Try "help" to get a list of possible commands.
smb: \> ls
  .                                   D        0  Fri Mar  6 20:25:45 2026
  ..                                  D        0  Fri Mar  6 20:25:45 2026
  dummy.txt                           N     1142  Wed Feb  4 21:22:17 2026
  flag.txt                            N       37  Fri Mar  6 20:25:45 2026

                65536 blocks of size 1024. 56896 blocks available
smb: \> cat flag.txt
cat: command not found
smb: \> nano flag.txt
nano: command not found
smb: \> get flag.txt
getting file \flag.txt of size 37 as flag.txt (12.0 KiloBytes/sec) (average 12.0 KiloBytes/sec)
smb: \> ^[[200~exit~
exit~: command not found
smb: \>  flag.txt
getting file \flag.txt of size 37 as flag.txt (12.0 KiloBytes/sec) (average 12.0 KiloBytes/sec)
smb: \> ^[[2
flag.txt: command not found
smb: \> exit
SebAcuna-picoctf@webshell:~$ ls
MY_GIT          flag.txt               level2.flag.txt.enc  myenv
README.txt      hash                   level2.py            node_modules
app.py          jwt.js                 level3.flag.txt.enc  package-lock.json
code.py         level1.flag.txt.enc    level3.hash.bin      package.json
codebook.txt    level1.flag.txt.enc.1  level3.py            runme.py
creds-dump.txt  level1.py              message.wav          serpentine.py
SebAcuna-picoctf@webshell:~$ cat flag.txt
picoCTF{5mb_pr1nter_5h4re5_7a400ec3}
```
#### Notas
#### Referencias
