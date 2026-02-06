# Download hidden files

`wget -r -np -nH -R "index.html*" -e robots=off http://10.13.247.192/.hidden/`

- `-r`: recursive mode
- `-np`: no parents directory
- `nH`: don't create directories
- `-R`: reject index.html
- `-e`: execute (robots.txt off)

**Flag** : d5eec3ec36cf80dce44a896f961c1831a05526ec215693c8f2c39543497d4466
