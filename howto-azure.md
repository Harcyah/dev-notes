# How to ... Azure !

## List repositories in a container registry

```
az acr repository list --name my_container_registry
```

## List tags in a repository

```
az acr repository show-tags --name my_container_registry --repository my_container_repository --orderby time_desc
```

## List locations

```
az account list-locations | jq '.[].name'
```

## Delete a tag

```
az acr repository delete --name my_container_registry --image my_container_repository:<tag> --yes
```

## Create a multiline secret

The web azure portal allows you to input a multiline value when creating/updating a secret but all breaks are removed afterwards ...

Let's use the cli instead:

```
az keyvault secret set --vault-name my_vault --name my_secret -f /path/to/my/file
```
