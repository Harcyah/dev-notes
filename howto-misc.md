# How to ... Misc !

## Generate a random file with given size

```
head -c 10M < /dev/urandom > <file>
```
or
```
dd if=/dev/urandom of=<file> bs=5MB count=1
```

## Create windows shortcut to java app with script

```
$shell = New-Object -ComObject WScript.Shell
$shortcut = $shell.CreateShortcut('C:\Users\<me>\<linkName>.lnk')
$shortcut.TargetPath = 'C:\path\to\java\bin\javaw.exe'
$shortcut.Arguments = '-Dfile.encoding=UTF-8 -jar C:\path\to\app.jar'
$shortcut.WorkingDirectory = 'C:\Users\<me>\'
$shortcut.Save()
```
