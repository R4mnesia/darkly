## Broken Access Control

`http://10.13.247.194/?page=b7e44c7a40c5f80139f0a50f3650fb2bd8d00b0d24667c4c2ca32c88e13b758f`
Regarder le code source de la page pour suivre les instruction de changement de `user agent` et de `referer` avec burp.

### Ce que ça implique / pourquoi c’est dangereux
L’attaquant peut ainsi :
- Avoir des accès supplémentaire.

### Comment la corriger
- Verifier la modification du `referer`

## CWE

-  CWE-284: Improper Access Control 
-  CWE-293: Using Referer Field for Authentication 