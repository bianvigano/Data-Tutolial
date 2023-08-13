Cara mencari file yang besar di linux

``“Cara mencari file yang besar di linux”``

## command nya :

Mencari file >=100 Mb di linux

```
find / -type f -size +100000k -exec ls -lh {} \; | awk '{ print $9 ": " $5 }'

find /var/ -type f -size +100000k -exec ls -lh {} \; | awk '{ print $9 ": " $5 }'
```

Mencari File >=100 Mb di path yang di tentukan ( /tmp)

```
find /tmp/ -type f -size +100000k -exec ls -lh {} \; | awk '{ print $9 ": " $5 }'
```

(Visited 60 times, 1 visits today)
