#### Descripción 
Connect to this PostgreSQL server and find the flag!
`psql -h saturn.picoctf.net -p 50833 -U postgres pico`
Password is `postgres`
#### Solución
 ```
 SebAcuna-academy@webshell:~$ psql -h saturn.picoctf.net -p 50833 -U postgres pico
Password for user postgres: 
psql (14.22 (Ubuntu 14.22-0ubuntu0.22.04.1), server 15.2 (Debian 15.2-1.pgdg110+1))
WARNING: psql major version 14, server major version 15.
         Some psql features might not work.
Type "help" for help.

pico=# select * from flags;
 id | firstname | lastname  |                address                 
----+-----------+-----------+----------------------------------------
  1 | Luke      | Skywalker | picoCTF{L3arN_S0m3_5qL_t0d4Y_21c94904}
  2 | Leia      | Organa    | Alderaan
  3 | Han       | Solo      | Corellia
(3 rows)

pico=# 
 ```
#### Notas

#### Referencias
