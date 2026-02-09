# Download hidden files

`wget -r -np -nH -R "index.html*" -e robots=off http://10.13.247.192/.hidden/`

- `-r`: recursive mode
- `-np`: no parents directory
- `nH`: don't create directories
- `-R`: reject index.html
- `-e`: execute (robots.txt off)

### Ce que ça implique / pourquoi c’est dangereux

L’attaquant peut ainsi :
- Télécharger des fichiers cachés sur le site.

### Comment la corriger

- Eviter de mettre des fichiers caché et téléchargeable par des utilisateurs sans privilèges spécifique.

## CWE

**CWE-434**: Unrestricted Upload of File with Dangerous Type
https://cwe.mitre.org/data/definitions/434.html