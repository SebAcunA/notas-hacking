#### Descripción 
Can you reverse a series of Linux text transformations to recover the original flag?

Additional details will be available after launching your challenge instance.
#### Solución
```
SebAcuna-picoctf@webshell:~$ nc foggy-cliff.picoctf.net 55901
===Welcome to the Text Transformations Challenge!===

Your goal: step by step, recover the original flag.
At each step, you'll see the transformed flag and a hint.
Enter the correct Linux command to reverse the last transformation.

--- Step 1 ---
Current flag: KW5xOW45OG43LWZhMDFnQHplMHNmYTRlRy1nazNnLXRhMWZlcmlyRShTR1BicHZj
Hint: Base64 encoded the string.
Enter the Linux command to reverse it: base64 -d
Correct!

--- Step 2 ---
Current flag: )nq9n98n7-fa01g@ze0sfa4eG-gk3g-ta1ferirE(SGPbpvc
Hint: Reversed the text.
Enter the Linux command to reverse it: rev 
Correct!

--- Step 3 ---
Current flag: cvpbPGS(Eriref1at-g3kg-Ge4afs0ez@g10af-7n89n9qn)
Hint: Replaced underscores with dashes.
Enter the Linux command to reverse it: mv
Incorrect. Try again.
Output: [Error] Command not allowed.
Hint: Try reversing: tr '_' '-'

Enter the Linux command to reverse it: tr 
Incorrect. Try again.
Output: [Error] Invalid tr usage. Example: tr 'a-z' 'n-za-m'
Hint: Try reversing: tr '_' '-'

Enter the Linux command to reverse it: tr '-' '_'
Correct!

--- Step 4 ---
Current flag: cvpbPGS(Eriref1at_g3kg_Ge4afs0ez@g10af_7n89n9qn)
Hint: Replaced curly braces with parentheses.
Enter the Linux command to reverse it: tr '{' '('
Incorrect. Try again.
Output: cvpbPGS(Eriref1at_g3kg_Ge4afs0ez@g10af_7n89n9qn)
Hint: Try reversing: tr '{}' '()'

Enter the Linux command to reverse it: tr '()' '{}'
Correct!

--- Step 5 ---
Current flag: cvpbPGS{Eriref1at_g3kg_Ge4afs0ez@g10af_7n89n9qn}
Hint: Applied ROT13 to letters.
Enter the Linux command to reverse it: ^C
SebAcuna-picoctf@webshell:~$ nc foggy-cliff.picoctf.net 55901
===Welcome to the Text Transformations Challenge!===

Your goal: step by step, recover the original flag.
At each step, you'll see the transformed flag and a hint.
Enter the correct Linux command to reverse the last transformation.

--- Step 1 ---
Current flag: KW5xOW45OG43LWZhMDFnQHplMHNmYTRlRy1nazNnLXRhMWZlcmlyRShTR1BicHZj
Hint: Base64 encoded the string.
Enter the Linux command to reverse it: base64 -d
Correct!

--- Step 2 ---
Current flag: )nq9n98n7-fa01g@ze0sfa4eG-gk3g-ta1ferirE(SGPbpvc
Hint: Reversed the text.
Enter the Linux command to reverse it: rev
Correct!

--- Step 3 ---
Current flag: cvpbPGS(Eriref1at-g3kg-Ge4afs0ez@g10af-7n89n9qn)
Hint: Replaced underscores with dashes.
Enter the Linux command to reverse it: tr '-' '_'
Correct!

--- Step 4 ---
Current flag: cvpbPGS(Eriref1at_g3kg_Ge4afs0ez@g10af_7n89n9qn)
Hint: Replaced curly braces with parentheses.
Enter the Linux command to reverse it: tr '()' '{}'
Correct!

--- Step 5 ---
Current flag: cvpbPGS{Eriref1at_g3kg_Ge4afs0ez@g10af_7n89n9qn}
Hint: Applied ROT13 to letters.
Enter the Linux command to reverse it: tr 'A-Za-z' 'N-ZA-Mn-za-m'
Correct!

Congratulations! You've recovered the original flag:
>>> picoCTF{Revers1ng_t3xt_Tr4nsf0rm@t10ns_7a89a9da}
```
#### Notas
Es necesario saber comandos básicos de linux para este reto
#### Referencias