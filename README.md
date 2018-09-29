# Dev Notes

## HOWTO : Unstash only certain files? [source](https://stackoverflow.com/questions/15264553/how-to-unstash-only-certain-files/22555169)

`git checkout stash@{0} -- <filename>`

## HOWTO : Change MacOS default shell [source](https://admin-serv.net/blog/560/debian-changer-le-shell-par-defaut-avec-chsh/)

Using `zsh/5.6.2` as an example.

- Add a new line like `/usr/local/Cellar/zsh/5.6.2/bin/zsh` to `/etc/shells`
- Change shell -> `chsh -s /usr/local/Cellar/zsh/5.6.2/bin/zsh`
