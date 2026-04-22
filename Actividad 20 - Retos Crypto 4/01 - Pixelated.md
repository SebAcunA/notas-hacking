#### Descripción 
I have these 2 images, can you make a flag out of them?[scrambled1.png](https://challenge-files.picoctf.net/c_wily_courier/e9637222852661fff9c7ef33644e4f2084ffe3c693d4efaad4d88eec98ddd3e4/scrambled1.png) [scrambled2.png](https://challenge-files.picoctf.net/c_wily_courier/e9637222852661fff9c7ef33644e4f2084ffe3c693d4efaad4d88eec98ddd3e4/scrambled2.png)
#### Solución
```
nano exp.py:
from PIL import Image
import numpy as np

foto1 = Image.open('scrambled1.png')
matriz1 = np.array(foto1)

foto2 = Image.open('scrambled2.png')
matriz2 = np.array(foto2)

matriz_resultante = matriz1 + matriz2

foto_final = Image.fromarray(matriz_resultante)

foto_final.save('resultado_suma.jpg')

foto_final.show()

```
#### Notas
La imagen resultante tiene la bandera y hay que transcribirla
#### Referencias
