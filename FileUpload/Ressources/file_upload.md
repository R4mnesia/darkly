## PHP File Upload

Changer le `Content-Type: application/x-php`.

```bash
------geckoformboundarye8da641c1728ca811ac3d4d824bc03af
Content-Disposition: form-data; name="uploaded"; filename="test.php"
Content-Type: application/x-php
```

```bash
------geckoformboundarye8da641c1728ca811ac3d4d824bc03af
Content-Disposition: form-data; name="uploaded"; filename="test.php"
Content-Type: image/jpeg
```

### Ce que ça implique / pourquoi c’est dangereux
L’attaquant peut ainsi :
- Upload un fichier php (ou autre) malveillant (ex: reverse shell).

### Comment la corriger
- Verifier le type de fichier et ne pas faire confiance au `Content-Type`.

## CWE

**CWE-434**: Unrestricted Upload of File with Dangerous Type
https://cwe.mitre.org/data/definitions/434.html