# Dockerfile for setting up a Postgres Flexible Server on Azure with Drizzle

## Contains

- Postgres Client Tools
- Azure CLI
- Drizzle Kit
- NodeJS 22

## How to use

Ensure you copy your migration script and migrations into the `/app` folder where drizzle kit is installed.

eg.

```dockerfile
ADD ./drizzle /app/drizzle
WORKDIR /app
```