## PHP File Upload

Change `Content-Type: application/x-php`.
The site trusts the `Content-Type` and does not verify the file type itself. So the attacker can upload a PHP file with malicious code to the website.
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

## CWE

**CWE-434**: Unrestricted Upload of File with Dangerous Type
https://cwe.mitre.org/data/definitions/434.html