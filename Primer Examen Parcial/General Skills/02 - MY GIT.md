#### Descripción 
I have built my own Git server with my own rules!You can clone the challenge repo using the command below.`git clone ssh://git@foggy-cliff.picoctf.net:57937/git/challenge.git`Here's the password: `1a03c9e3`Check the README to get your flag!
#### Solución
```
SebAcuna-picoctf@webshell:~/MY_GIT/challenge$ cat README.md
# MyGit

### If you want the flag, make sure to push the flag!

Only flag.txt pushed by ```root:root@picoctf``` will be updated with the flag.

GOOD LUCK!
SebAcuna-picoctf@webshell:~/MY_GIT/challenge$ git config user.name "root"
SebAcuna-picoctf@webshell:~/MY_GIT/challenge$ git config user.email "root@picoctf"
SebAcuna-picoctf@webshell:~/MY_GIT/challenge$ 
SebAcuna-picoctf@webshell:~/MY_GIT/challenge$ echo "placeholder" > flag.txt
SebAcuna-picoctf@webshell:~/MY_GIT/challenge$ git add flag.txt
SebAcuna-picoctf@webshell:~/MY_GIT/challenge$ git commit -m "add flag.txt"
[master f38af7f] add flag.txt
 1 file changed, 1 insertion(+)
 create mode 100644 flag.txt
SebAcuna-picoctf@webshell:~/MY_GIT/challenge$ git push
git@foggy-cliff.picoctf.net's password: 
Enumerating objects: 4, done.
Counting objects: 100% (4/4), done.
Delta compression using up to 2 threads
Compressing objects: 100% (2/2), done.
Writing objects: 100% (3/3), 278 bytes | 278.00 KiB/s, done.
Total 3 (delta 0), reused 0 (delta 0), pack-reused 0
remote: Author matched and flag.txt found in commit...
remote: Congratulations! You have successfully impersonated the root user
remote: Here's your flag: picoCTF{1mp3rs0n4t4_g17_345y_367122f4}
To ssh://foggy-cliff.picoctf.net:57937/git/challenge.git
   088b58f..f38af7f  master -> master
SebAcuna-picoctf@webshell:~/MY_GIT/challenge$ 
```
#### Notas
#### Referencias