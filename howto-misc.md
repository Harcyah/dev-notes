# How to ... Misc !

## Generate a random file with given size

```
head -c 10M < /dev/urandom > <file>
```
or
```
dd if=/dev/urandom of=<file> bs=5MB count=1
```
