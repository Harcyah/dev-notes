# How to ... Sed !

## Delete line [source](https://stackoverflow.com/questions/5410757/delete-lines-in-a-text-file-that-contain-a-specific-string)
   
```
sed -i '/pattern to match/d' /path/to/file
```

## Print even lines [source](https://unix.stackexchange.com/questions/26723/print-odd-numbered-lines-print-even-numbered-lines)

```
sed -n 'n;p' /path/to/file
```

## Print odd lines

```
sed -n 'p;n' /path/to/file
```

## Remove backquotes from $file
   
```
sed 's/`//g' <file>
```
