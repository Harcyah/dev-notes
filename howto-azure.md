# How to ... Azure !

## List repositories in a container registry

```
az acr repository list --name my_container_registry
```

## List tags in a repository

```
az acr repository show-tags --name my_container_registry --repository my_container_repository --orderby time_desc
```

## Delete a tag

```
az acr repository delete --name my_container_registry --image my_container_repository:<tag> --yes
```
