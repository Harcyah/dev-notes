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

## Replace a line

Given:
```
One morning, when Gregor Samsa woke from troubled dreams
he found himself transformed in his bed into a horrible vermin
```

When:
```
sed 's/.*Gregor Samsa.*/In the week before their departure to Arrakis/g' test.txt
```

Then:
```
In the week before their departure to Arrakis
he found himself transformed in his bed into a horrible vermin
```

## Insert line after match

Given:
```
One morning, when Gregor Samsa woke from troubled dreams
he found himself transformed in his bed into a horrible vermin
```

When:
```
sed '/.*transformed in his bed.*/a This was really disgusting' test.txt
```

Then:
```
One morning, when Gregor Samsa woke from troubled dreams
he found himself transformed in his bed into a horrible vermin
This was really disgusting
```

## Insert line before match

Given:
```
One morning, when Gregor Samsa woke from troubled dreams
he found himself transformed in his bed into a horrible vermin
```

When:
```
sed '/.*transformed in his bed.*/i (large hangover)' test.txt
```

Then:
```
One morning, when Gregor Samsa woke from troubled dreams
(large hangover)
he found himself transformed in his bed into a horrible vermin
```
