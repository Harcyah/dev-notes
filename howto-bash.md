# How to ... Bash !

## Shebang! [source](https://ashishb.net/all/the-first-two-statements-of-your-bash-script-should-be/)

```
#!/usr/bin/env bash
set -euo pipefail
```

## Readonly variables

```
local -r TEXT="lorem ipsum"
```

## Parameters

Fail if parameter isn't set: 
```
VERSION=${1:?"Please give a parent version as arg 1"}
```

Use default value if parameter isn't set: 
```
VERSION=${1:-Whatever}
```

## Case convert

VAR="Hello World"
echo ${VAR,} 
=> "hello World"

VAR="Hello World"
echo ${VAR,,}
=> "hello world"

VAR="hello world"
echo ${VAR^^}
=> "Hello world"

VAR="hello world"
echo ${VAR^^}
=> "HELLO WORLD"
