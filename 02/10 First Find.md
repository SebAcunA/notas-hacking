#### Descripción 
Unzip this archive and find the file named 'uber-secret.txt'

- [Download zip file](https://artifacts.picoctf.net/c/502/files.zip)
#### Solución
```
SebAcuna-picoctf@webshell:~$ ls
files  files.zip
SebAcuna-picoctf@webshell:~$ cd files
SebAcuna-picoctf@webshell:~/files$ ls
13771.txt.utf-8  acceptable_books  satisfactory_books
14789.txt.utf-8  adequate_books
SebAcuna-picoctf@webshell:~/files$ cd
SebAcuna-picoctf@webshell:~$ find -name uber*
./files/adequate_books/more_books/.secret/deeper_secrets/deepest_secrets/uber-secret.txt
SebAcuna-picoctf@webshell:~$ cat ./files/adequate_books/more_books/.secret/deeper_secrets/deepest_secrets/uber-secret.txt
picoCTF{f1nd_15_f457_ab443fd1}
SebAcuna-picoctf@webshell:~$ 
```
#### Notas
#### Referencias
