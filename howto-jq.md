# How to ... Jq !

## Given a list of projects with tags, get all distinct tags

Given:
```json
{
  "projects": [{
    "name": "project-a",
    "tags": [ "tag-1", "tag-2" ]
  }, {
     "name": "project-b",
     "tags": [ "tag-3", "tag-2" ]
  }]
}
```

When:
```shell script
jq '.projects[].tags[] ' | sort | uniq
```

Then:
```shell script
"tag-1"
"tag-2"
"tag-3"
```
