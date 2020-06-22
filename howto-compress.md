# How to ... Compress !

## With unzip

`unzip <archive>`  
Uncompress <archive> in current folder

`unzip <archive> -d <output_folder>`  
Uncompress <archive> to <output_folder>

`unzip -l <archive>`  
List <archive> contents

`unzip -j <archive>`  
List <archive> contents, trashing any subfolder

## With bsdtar

`bsdtar -xf <archive>`  
Uncompress <archive> in current folder

`bsdtar -xf <archive> -C <output_folder>`  
Uncompress <archive> to <output_folder>

`bsdtar -xf <archive> --strip-components=N`  
Uncompress <archive>, trashing N first subfolders
