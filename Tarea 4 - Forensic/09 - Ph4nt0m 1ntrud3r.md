#### Descripción 
A digital ghost has breached my defenses, and my sensitive data has been stolen! 😱💻 Your mission is to uncover how this phantom intruder infiltrated my system and retrieve the hidden flag.To solve this challenge, you'll need to analyze the provided PCAP file and track down the attack method. The attacker has cleverly concealed his moves in well timely manner. Dive into the network traffic, apply the right filters and show off your forensic prowess and unmask the digital intruder!Find the PCAP file here [Network Traffic PCAP file](https://challenge-files.picoctf.net/c_verbal_sleep/45a9df82c8f05fd74b8547d157ae6b1be6ba783a2bad55c6f8c664e4609d88ac/myNetworkTraffic.pcap) and try to get the flag.
#### Solución
```bash
wireshark captura.pcap
```
Dado que el flag está fragmentado en paquetes pequeños, aplicamos un filtro por longitud para aislar únicamente los paquetes relevantes:
- En la barra de filtros escribimos:
```
frame.len == 12 || frame.len == 4
```
Esto reduce significativamente la cantidad de paquetes y elimina ruido irrelevante.
O bien abrir Wireshark de forma gráfica y cargar el archivo desde `File > Open`.
Una vez aplicado el filtro, ordenamos los paquetes por **tiempo de llegada** haciendo clic en la columna `Time` para asegurarnos de leerlos en el orden correcto en que fueron enviados.
Para cada paquete en la lista:
1. Clic derecho sobre el paquete → **Follow > TCP Stream** (o simplemente seleccionarlo)
2. En el panel inferior, ir a la sección de bytes
3. Seleccionar el paquete → en el menú: `Analyze > Show Packet Bytes`
4. En la ventana emergente, cambiar la vista a **ASCII** o **Raw**
5. Anotar el carácter o bytes visibles
Repetir este proceso **uno por uno**, en orden cronológico, anotando cada carácter obtenido.
6. Reconstruir el flag
Al concatenar todos los bytes/caracteres extraídos en orden, se forma el flag completo:
```
picoCTF{1t_w4snt_th4t_34sy_tbh_4r_f318db22}
```
#### Notas
#### Referencias

