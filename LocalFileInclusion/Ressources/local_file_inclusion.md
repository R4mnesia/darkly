## Local file inclusion

`http://10.13.247.192/index.php?page=../../../../../../../etc/passwd`

### Ce que ça implique / pourquoi c’est dangereux

L’attaquant peut ainsi :
- Lire des fichiers du serveurs comme etc/passwd

### Comment la corriger

- Mieux parser les entrées utilisateurs au niveau du backend.
- Restreindre l'accès utilisateurs.

## CWE

**CWE-23**: Relative Path Traversal: `https://cwe.mitre.org/data/definitions/23.html`