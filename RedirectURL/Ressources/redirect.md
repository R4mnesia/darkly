## URL redirection to Untrusted Site

Change redirection with google.com for example:
- `<li><a href="index.php?page=redirect&site=facebook" class="icon fa-facebook"></a></li>`
- `<li><a href="index.php?page=redirect&site=google.com" class="icon fa-facebook"></a></li>`

### Ce que ça implique / pourquoi c’est dangereux
L’attaquant peut ainsi :

- Rediriger l'URL vers un site malveillant

Cela montre un **accès non autorisé complet aux données** de la base.

### Comment la corriger
- Verifier dans le backend que les redirections de site ne peuvent etre modifiées.
- Eviter les redirections et mettre un lien direct.

## CWE

**CWE-601**: URL Redirection to Untrusted Site
https://cwe.mitre.org/data/definitions/601.html
