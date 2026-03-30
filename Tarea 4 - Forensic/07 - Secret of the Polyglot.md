#### Descripción 
The Network Operations Center (NOC) of your local institution picked up a suspicious file, they're getting conflicting information on what type of file it is. They've brought you in as an external expert to examine the file. Can you extract all the information from this strange file?Download the suspicious file [here](https://artifacts.picoctf.net/c_titan/97/flag2of2-final.pdf).
#### Solución
```
Abrir el pdf directamente y ver la segunda parte de la flag: 1n_pn9_&_pdf_724b1287}

Para la primera parte:
┌──(kali㉿kali)-[~/forensic/Polyglot]
└─$ cp flag2of2-final.pdf flag.png

┌──(kali㉿kali)-[~/forensic/Polyglot]
└─$ xdg-open flag.png 

picoCTF{f1u3n7_
Renombrar porque el archivo es un Polyglot (es PNG y PDF al mismo tiempo)

FLAG COMPLETA: picoCTF{f1u3n7_1n_pn9_&_pdf_724b1287}
```
#### Notas
#### Referencias
