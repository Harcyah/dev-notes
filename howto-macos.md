# How to ... MacOS !

## Change default shell [source](https://admin-serv.net/blog/560/debian-changer-le-shell-par-defaut-avec-chsh/)

Using `zsh/5.6.2` as an example.

- Add a new line like `/usr/local/Cellar/zsh/5.6.2/bin/zsh` to `/etc/shells`
- Change shell -> `chsh -s /usr/local/Cellar/zsh/5.6.2/bin/zsh`
