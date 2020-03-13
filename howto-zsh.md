# How to ... Zsh !

## String manipulation
   
```
BLABLA='Servez à ce monsieur une bière et des kiwis'
```

```
# Length
echo ${#BLABLA}
> 43
```

```
# Substring : by index (starts at 1)
echo $BLABLA[12,20]
> monsieur
```

```
# Substring : by start/length (starts at 1)
echo ${BLABLA:12:8}
> monsieur
```

```
# Substring : negative index : don't forget the space before the minus symbol
echo ${BLABLA: -5}
> kiwis
```
