# How to ... Notepad++ !

## Split long string to given length

- Select all text
- Open "find & replace"
- Toggle on regex mode 
- Search `.{80}(?!\R)`, replace with `$0\r\n`
