# How to ... Git !

## Diff of the same file between 2 tags [source](https://stackoverflow.com/questions/3211809/how-to-compare-two-tags)

```
git diff v1.10.2 v2.1.0 -- path/to/my/file
```

## Unstash only one particular file [source](https://stackoverflow.com/questions/15264553/how-to-unstash-only-certain-files/22555169)

`git checkout stash@{0} -- <filename>`

## Cleanup [source](https://rtyley.github.io/bfg-repo-cleaner/)

`git reflog expire --expire=now --all && git gc --prune=now --aggressive`
