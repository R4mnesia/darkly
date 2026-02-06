## XSS DOM based

Cela permet d'executer du javascript en contournant une règle de sécurité via l'encodage de la balise `<script>` en base64.
`data:text/html;base64,PHNjcmlwdD5hbGVydCgnWFNTJyk8L3NjcmlwdD4K`

### Ce que ça implique / pourquoi c’est dangereux

L’attaquant peut ainsi :
- Permet d'executer du javascript

### Comment la corriger
- Meilleur parsing

## CWE

CWE-79: Improper Neutralization of Input During Web Page Generation ('Cross-site Scripting')