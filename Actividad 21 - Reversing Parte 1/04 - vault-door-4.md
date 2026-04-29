#### Descripción 
This vault uses ASCII encoding for the password.The source code for this vault is here: [VaultDoor4.java](https://challenge-files.picoctf.net/c_fickle_tempest/92aa3358fb5bde2c6f38b39fbf2d59af8c44220bc0662ce636d655f0ad3a1a8d/VaultDoor4.java)
#### Solución
```
┌──(kali㉿kali)-[~/picoctf/reversing/VaultDoor4]
└─$ java VaultDoor4.java
Enter vault password: 678910293810293810928310923
jU5t_4_bUnCh_0f_bYt3s_b4e943c3a0
Access granted.
                                                                                            
┌──(kali㉿kali)-[~/picoctf/reversing/VaultDoor4]
└─$ cat VaultDoor4.java 
import java.util.*;

class VaultDoor4 {
    public static void main(String args[]) {
        VaultDoor4 vaultDoor = new VaultDoor4();
        Scanner scanner = new Scanner(System.in);
        System.out.print("Enter vault password: ");
        String userInput = scanner.next();
        String input = userInput.substring("picoCTF{".length(),userInput.length()-1);
        if (vaultDoor.checkPassword(input)) {
            System.out.println("Access granted.");
        } else {
            System.out.println("Access denied!");
        }
    }

    // I made myself dizzy converting all of these numbers into different bases,
    // so I just *know* that this vault will be impenetrable. This will make Dr.
    // Evil like me better than all of the other minions--especially Minion
    // #5620--I just know it!
    //
    //  .:::.   .:::.
    // :::::::.:::::::
    // :::::::::::::::
    // ':::::::::::::'
    //   ':::::::::'
    //     ':::::'
    //       ':'
    // -Minion #7781
    public boolean checkPassword(String password) {
        byte[] passBytes = password.getBytes();
        byte[] myBytes = {
            106 , 85  , 53  , 116 , 95  , 52  , 95  , 98  ,
            0x55, 0x6e, 0x43, 0x68, 0x5f, 0x30, 0x66, 0x5f,
            0142, 0131, 0164, 063 , 0163, 0137, 0142, 064 ,
            'e' , '9' , '4' , '3' , 'c' , '3' , 'a' , '0' ,
        };
        /*for (int i=0; i<32; i++) {
            if (passBytes[i] != myBytes[i]) {
                return false;
            }
        }*/
        String flag = new String(myBytes);
        System.out.println(flag);
        return true;
    }
}

```
#### Notas
#### Referencias
