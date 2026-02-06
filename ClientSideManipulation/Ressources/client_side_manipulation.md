# Client side manipulation

`http://10.13.247.194/index.php?page=survey#`
```html
<SELECT name="valeur" onChange='javascript:this.form.submit();'>
	<option value="1">1</option>
	<option value="2">2</option>
	<option value="3">3</option>
	<option value="4">4</option>
	<option value="5">5</option>
	<option value="6">6</option>
	<option value="7">7</option>
	<option value="8">8</option>
	<option value="9">9</option>
	<option value="10">10</option>
</SELECT>
```
Si on change la `value`, le code js ne vérifie pas et l'enregistre dans la db peut importe le nombre.

### Ce que ça implique / pourquoi c’est dangereux

L’attaquant peut ainsi :
- Ajouter des valeurs que le site ne propose pas.

### Comment la corriger
- Parser la variable `value` au moment du POST.

## CWE
CWE-602: Client-Side Enforcement of Server-Side Security 