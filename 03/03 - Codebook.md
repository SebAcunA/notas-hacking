#### Descripción 
Run the Python script `code.py` in the same directory as `codebook.txt`.
- [Download code.py](https://artifacts.picoctf.net/c/3/code.py)
- [Download codebook.txt](https://artifacts.picoctf.net/c/3/codebook.txt)
#### Solución
```
SebAcuna-picoctf@webshell:~$ wget https://artifacts.picoctf.net/c/3/code.py
--2026-02-17 02:20:11--  https://artifacts.picoctf.net/c/3/code.py
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 3.170.131.33, 3.170.131.72, 3.170.131.77, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|3.170.131.33|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 1278 (1.2K) [application/octet-stream]
Saving to: 'code.py'

code.py               100%[=======================>]   1.25K  --.-KB/s    in 0s      

2026-02-17 02:20:11 (1015 MB/s) - 'code.py' saved [1278/1278]

SebAcuna-picoctf@webshell:~$ https://artifacts.picoctf.net/c/3/codebook.txt
-bash: https://artifacts.picoctf.net/c/3/codebook.txt: No such file or directory
SebAcuna-picoctf@webshell:~$ wget https://artifacts.picoctf.net/c/3/codebook.txt
--2026-02-17 02:20:41--  https://artifacts.picoctf.net/c/3/codebook.txt
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 3.170.131.18, 3.170.131.77, 3.170.131.33, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|3.170.131.18|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 27 [application/octet-stream]
Saving to: 'codebook.txt'

codebook.txt          100%[=======================>]      27  --.-KB/s    in 0s      

2026-02-17 02:20:42 (19.6 MB/s) - 'codebook.txt' saved [27/27]

SebAcuna-picoctf@webshell:~$ python codebook.py
python: can't open file '/home/SebAcuna-picoctf/codebook.py': [Errno 2] No such file or directory
SebAcuna-picoctf@webshell:~$ ls
README.txt    level1.flag.txt.enc    level2.flag.txt.enc  level3.hash.bin
code.py       level1.flag.txt.enc.1  level2.py            level3.py
codebook.txt  level1.py              level3.flag.txt.enc  runme.py
SebAcuna-picoctf@webshell:~$ python code.py
picoCTF{c0d3b00k_455157_197a982c}
```
#### Notas
#### Referencias