# How to ... Batch !

## Get current batch folder [source](https://stackoverflow.com/a/16255331)

```
%~dp0
```

## Move all files from subfolders to another folder [source](https://www.winhelponline.com/blog/move-copy-files-multiple-sub-folders-single-folder/)

```
cd parent-of-subfolders
for /r %d in (*) do move /Y "%d" "d:\target"
```
