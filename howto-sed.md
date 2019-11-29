# How to ... Sed !

## Delete line [source](https://stackoverflow.com/questions/5410757/delete-lines-in-a-text-file-that-contain-a-specific-string)
   
```
sed -i '/pattern to match/d' /path/to/file
```

## Print even or odd lines [source](https://unix.stackexchange.com/questions/26723/print-odd-numbered-lines-print-even-numbered-lines)
   
Even lines
```
sed -n 'n;p' /path/to/file
```

Odd Lines
```
sed -n 'p;n' /path/to/file
```

## Replace quotes
   
Remove backquotes from $file:
```
sed 's/`//g' <file>
```
