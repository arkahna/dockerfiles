FROM node:22-bookworm-slim

RUN apt-get update
RUN apt-get install -y curl postgresql-client jq
RUN curl -fsSL https://deb.nodesource.com/setup_22.x -o nodesource_setup.sh | bash
RUN curl -sL https://aka.ms/InstallAzureCLIDeb | bash

RUN mkdir /app
WORKDIR /app

RUN npm install drizzle-orm@latest drizzle-kit@latest pg@latest