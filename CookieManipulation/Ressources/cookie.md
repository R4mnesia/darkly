## Falsification de cookie

- `b326b5062b2f0e69046810717534cb09` = **true**
- `68934a3e9455fa72420237eb05902327` = **false**
- Crack le cookie avec crackstation: https://crackstation.net/

### Ce que ça implique / pourquoi c’est dangereux
L’attaquant peut ainsi :
- Se connecter avec un utilisateur admin

Cela montre un **accès non autorisé complet aux données** de la base.

### Comment la corriger
- Utiliser des token JWT pour la connexion
- Utiliser un chiffrement fort (AES)

### CWE

- **CWE-327**: Use of a Broken or Risky Cryptographic Algorithm 
- **CWE-326**: Inadequate Encryption Strength