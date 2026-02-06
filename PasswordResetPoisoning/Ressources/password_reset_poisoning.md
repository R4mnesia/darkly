# Password reset poisoning change email

`POST http://10.12.248.26/index.php?page=recover`
```html
<form action="#" method="POST">
	<input type="hidden" name="mail" value="webmaster@borntosec.com" maxlength="15">
	<input type="submit" name="Submit" value= "Submit">
</form>
```
Changer l'email par un email malveillant.

### Ce que ça implique / pourquoi c’est dangereux
L’attaquant peut ainsi :

- Recevoir un mail pour changer le mot de passe de webmaster

### Comment la corriger

- Vérifier l'email au moment du post

## CWE
