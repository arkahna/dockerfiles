# Dockerfile for setting up a Postgres Flexible Server on Azure with Drizzle

## Contains

-   Postgres Client Tools
-   Azure CLI
-   Drizzle Kit
-   NodeJS 22

## How to use

Ensure you copy your migration script and migrations into the `/app` folder where drizzle kit is installed.

eg.

```dockerfile
FROM azure-postgres-drizzle-migrations

ADD ./drizzle /app/drizzle
WORKDIR /app
```

## ACR Build Task

To use this image in ACR. You can use the following build task.

```bash
az acr task create \
  --name azure-postgres-drizzle-migrations \
  --registry <registry name> \
  --subscription <subscription id> \
  --platform linux/amd64 \
  --context https://github.com/arkahna/dockerfiles\#main:azure-postgres-drizzle-migrations \
  --image azure-postgres-drizzle-migrations:latest \
  --file Dockerfile \
  --commit-trigger-enabled false \
  --schedule "0 0 * * *" \
  --base-image-trigger-enabled true
```

Then change the FROM to be

```dockerfile
FROM <registryname>.azurecr.io/azure-postgres-drizzle-migrations
```
