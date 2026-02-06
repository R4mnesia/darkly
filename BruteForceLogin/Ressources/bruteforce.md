## Vulnérabilité : Brute force de mot de passe

```
Test soit de toutes les possibilites des mot de passe, soit comme ici on test des mots de passe provenant de Rockyou.txt, apparue suite à une importante fuite de données en 2009 , contenant des mots de passe couramment utilisés

Pour se faire on utilise hydra qui va tester les mots de passe pour nous, normalement il faudrait connaitre le nom d'un utilisateur dont on veut trouver le mdp, ici on mettra webmaster.
On stipule que les mots de pass qui vont etre testés viendront du fichier rockyou.txt.
On donne l'adresse du site et le type d'envoi ici http-get-form.
"/index.php:page=signin&username=^USER^&password=^PASS^&Login=Login:F=images/WrongAnswer.gif"
F=images/WrongAnswer.gif signale que c'est false quand on recoit le gif wronganswer, sans ca le programme s'arrete des qu'on a une reponse du site avec le premier mdp testé.

On obtient:
[80][http-get-form] host: 10.13.247.194   login: webmaster   password: shadow
[STATUS] attack finished for 10.13.247.194 (valid pair found)
1 of 1 target successfully completed, 1 valid password found


Dans la page "http://10.13.247.194/?page=signin" le mdp shadow donne le flag b3a6e43ddf8b4bbb4125e5e7d23040433827759d4de1c04ea63907479a80a6b2
```

### Ce que ça implique / pourquoi c’est dangereux
L’attaque brute force permet de recuperer des mots de passe et ainsi se connecter avec le compte d'une autre personne pour recuperer ses donnees ou usurper son identite


### Comment la corriger
- Consigne pour le mdp ex: minimum de caractères, majuscules, caractère numérique et spéciaux obligatoires
- Bloquer les mdp trop communs ou où les caractères se répètent
- Proposer géneration mdp aléatoire
- Autoriser qu'un nombre limité d'erreurs avant verrouillage du système
- Limiter le nombre de tentatives par unité de temps

### Type de CWE
- **CWE-307** — Improper Restriction of Excessive Authentication Attempts
