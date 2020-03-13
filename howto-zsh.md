# How to ... Zsh !

## String manipulation
   
```
BLABLA='Servez à ce monsieur une bière et des kiwis'
```

```shell script
# Length
% echo ${#BLABLA}
> 43
```

```shell script
# Substring : by index (starts at 1)
% echo $BLABLA[12,20]
> monsieur
```

```shell script
# Substring : by start/length (starts at 1)
% echo ${BLABLA:12:8}
> monsieur
```

```shell script
# Substring : negative index : don't forget the space before the minus symbol
% echo ${BLABLA: -5}
> kiwis
```

```shell script
# Substring before token
% echo ${BLABLA% monsieur*}                                                                                                              :) [0.020s] [2020-03-13 09:11:31]
> Servez à ce
```

```shell script
# Substring after token
% echo ${BLABLA#*monsieur }                                                                                                               :) [0.019s] [2020-03-13 09:12:26]
> une bière et des kiwis
```

```shell script
# Change case
% echo ${(L)BLABLA}
> servez à ce monsieur une bière et des kiwis
% echo ${(U)BLABLA}
> SERVEZ À CE MONSIEUR UNE BIÈRE ET DES KIWIS
```
