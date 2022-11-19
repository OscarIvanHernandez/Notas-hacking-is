# PicoCTF2019 Reversing
## Objetivo
This vault uses ASCII encoding for the password. The source code for this vault is here: [VaultDoor4.java](https://jupiter.challenges.picoctf.org/static/834acd392e0964a41f05790655a994b9/VaultDoor4.java)
## Pistas
Use a search engine to find an "ASCII table".

You will also need to know the difference between octal, decimal, and hexadecimal numbers.

## Solucion

┌─[oscar@oscar-parrot]─[~/reversing/2019/vault-door-4]
└──╼ $ls
VaultDoor4.java
┌─[oscar@oscar-parrot]─[~/reversing/2019/vault-door-4]
└──╼ $nano VaultDoor4.java 
┌─[oscar@oscar-parrot]─[~/reversing/2019/vault-door-4]
└──╼ $  
   GNU nano 5.4                                                                           VaultDoor4.java                                                                                    
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
            0142, 0131, 0164, 063 , 0163, 0137, 0146, 064 ,
            'a' , '8' , 'c' , 'd' , '8' , 'f' , '7' , 'e' ,
        };
        for (int i=0; i<32; i++) {
            if (passBytes[i] != myBytes[i]) {
                return false;
            }
        }
        return true;
    }
}


Usando una consola en Mozilla se puede hacer lo siguiente
	captura


picoCTF{jU5t_4_bUnCh_0f_bYt3s_f4a8cd8f7e}

## Notas adicionales
## Referencias 
