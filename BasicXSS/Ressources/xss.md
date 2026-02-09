## XSS

- `http://10.11.248.36/?page=feedback`
- `<script>alert("a");</script>`

### Ce que ça implique / pourquoi c’est dangereux

L’attaquant peut ainsi :
- Permet d'executer du javascript

### Comment la corriger
- Avoir un meilleur parsing

## CWE

- CWE-79: Improper Neutralization of Input During Web Page Generation ('Cross-site Scripting')