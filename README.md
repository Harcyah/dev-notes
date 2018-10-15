# Dev Notes

## HOWTO : Git : Unstash only one particular file [source](https://stackoverflow.com/questions/15264553/how-to-unstash-only-certain-files/22555169)

`git checkout stash@{0} -- <filename>`

## HOWTO : MacOS : Change default shell [source](https://admin-serv.net/blog/560/debian-changer-le-shell-par-defaut-avec-chsh/)

Using `zsh/5.6.2` as an example.

- Add a new line like `/usr/local/Cellar/zsh/5.6.2/bin/zsh` to `/etc/shells`
- Change shell -> `chsh -s /usr/local/Cellar/zsh/5.6.2/bin/zsh`

## HOWTO : MySQL : Compute RIBPS [source](https://dba.stackexchange.com/questions/39467/mysql-performance-impact-of-increasing-innodb-buffer-pool-size)

RIBPS stands for `Recommended InnoDB Buffer Pool Size`

```
SELECT CEILING(SUM(data_length+index_length)/POWER(1024,2)) RIBPS FROM information_schema.tables WHERE engine='InnoDB';
```

## HOWTO : Git : Diff of the same file between 2 tags [source](https://stackoverflow.com/questions/3211809/how-to-compare-two-tags)

```
git diff v1.10.2 v2.1.0 -- path/to/my/file
```

## HOWTO : Sheel : Print even or odd lines [source](https://unix.stackexchange.com/questions/26723/print-odd-numbered-lines-print-even-numbered-lines)


Even lines
```
sed -n 'n;p' /path/to/file
```

Odd Lines
```
sed -n 'p;n' /path/to/file
```

## Books

| Author | Title |
|---|--|
| Andrew Hunt | 	The Pragmatic Programmer: From Journeyman to Master |
| Edmond Lau |	The Effective Engineer |
| Martin Fowler |	Refactoring: Improving the Design of Existing Code |
| Peter Seibel |	Coders at Work: Reflections on the Craft of Programming |
| Robert C. Martin |	Clean Code: A Handbook of Agile Software Craftsmanship |
| Robert C. Martin |	The Clean Coder: A Code of Conduct for Professional Programmers |
| Sandro Mancuso |	The Software Craftsman: Professionalism, Pragmatism, Pride |
| Steve Freeman |	Growing Object-Oriented Software, Guided by Tests |
| Steve McConnell |	Code Complete |
