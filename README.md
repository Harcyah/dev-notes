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

## HOWTO : Docker : Start bash in running container [source](https://gist.github.com/mitchwongho/11266726)

```
docker run -it <container> /bin/bash
```

## HOWTO : Git : Diff of the same file between 2 tags [source](https://stackoverflow.com/questions/3211809/how-to-compare-two-tags)

```
git diff v1.10.2 v2.1.0 -- path/to/my/file
```

## HOWTO : Batch : Get current batch folder [source](https://stackoverflow.com/a/16255331)

```
%~dp0
```

## HOWTO : Batch : Move all files from subfolders to another folder [source](https://www.winhelponline.com/blog/move-copy-files-multiple-sub-folders-single-folder/)

```
cd parent-of-subfolders
for /r %d in (*) do move /Y "%d" "d:\target"
```

## HOWTO : Maven : Run a plugin execution from CLI [source](https://stackoverflow.com/questions/3166538/how-to-execute-maven-plugin-execution-directly-from-command-line/28642594)

```
>mvn <plugin group>:<plugin artifact>:<plugin goal>@<execution id>
```

## HOWTO : Shell : Print even or odd lines [source](https://unix.stackexchange.com/questions/26723/print-odd-numbered-lines-print-even-numbered-lines)

Even lines
```
sed -n 'n;p' /path/to/file
```

Odd Lines
```
sed -n 'p;n' /path/to/file
```

## HOWTO : Sed : Delete line [source](https://stackoverflow.com/questions/5410757/delete-lines-in-a-text-file-that-contain-a-specific-string)

```
sed -i '/pattern to match/d' /path/to/file
```

## HOWOT : Shell : Replace quotes

Remove backquotes from $file:
```
sed 's/`//g' <file>
```

Replace `\'` with `''`
```
tr "\\\'" "''" < file1 > file2
```

## HOWTO : Intellij : Create unit or integration tests configuration

- Create JUnit run/debug configuration
- Use `Pattern` test kind
- Set pattern to `^.*IntegrationTest$` to only run integration tests
- Set pattern to `^(?!.*IntegrationTest$).*$` to only run unit tests

This configuration obviously depends on a correct class naming pattern :)

## WSL Notes

Root FS: `%LocalAppData%\Packages\CanonicalGroupLimited.Ubuntu18.04onWindows_79rhkp1fndgsc\LocalState\rootfs`

App path: `C:\Program Files\WindowsApps\CanonicalGroupLimited.Ubuntu18.04onWindows_1804.2018.817.0_x64__79rhkp1fndgsc`

## Books

| Author(s) | Title |
|---|---|
| Andrew Hunt | The Pragmatic Programmer: From Journeyman to Master |
| Edmond Lau | The Effective Engineer |
| Martin Fowler | Refactoring: Improving the Design of Existing Code |
| Peter Seibel | Coders at Work: Reflections on the Craft of Programming |
| Robert C. Martin | Clean Code: A Handbook of Agile Software Craftsmanship |
| Robert C. Martin | The Clean Coder: A Code of Conduct for Professional Programmers |
| Sandro Mancuso | The Software Craftsman: Professionalism, Pragmatism, Pride |
| Steve Freeman | Growing Object-Oriented Software, Guided by Tests |
| Steve McConnell | Code Complete |
| Alan Shalloway, Scott Bain, Ken Pugh & Amir Kolsky | Essential Skills for the Agile Developer: A Guide to Better Programming and Design |
| John Sonmez | Soft Skills: The software developer's life manual |
| Eric Freeman, Bert Bates, Kathy Sierra, Elisabeth Robson | Head First Design Patterns: A Brain-Friendly Guide |

## Things I don't know

Inspired by [overreacted](https://overreacted.io/things-i-dont-know-as-of-2018/)

- Non-trivial bash scripting. Commands such as `xargs` are complete mystery to me. I can't remember how to write most of conditionals, I have to google it every time.
- Low-level languages : I once wrote Assembly (which flavor ?) in school, like 15 years ago.
- Networking : I know the big picture, but most of the protocols are complete black boxes to me. I collapse in tears every time I have to configure anything related to networking.
- AWS / Azure : I played a bit with both, I vaguely know how to start a docker container, and configure properties or fire basic services, but that's all.
- Kubernetes, Terraform : I probably can fix a typo in it, but that's all.
- Python : I wrote my first non-trivial script one week ago.
- Perl : Never used it.
- Ruby : I used it for some helper scripts around, but I constantly have to google for loops, classes, and such
- Modern Javascript : I used to be fluent in JS dev during the JQuery / AngularJS (aka. Angular 1) ages, but I completely lost it. Webpack, Vue, React, etc : I played a bit with all those, I'm not convinced, and I can't spend time learning new framework / toolchain every 6 months.
- Maths : I suck at it.
- CSS : Float is a mystery to me. Heard about flexbox and grid but never tried them.
