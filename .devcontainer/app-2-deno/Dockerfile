ARG DENO_VERSION=1.42.3

FROM denoland/deno:bin-$DENO_VERSION AS deno
FROM mcr.microsoft.com/devcontainers/typescript-node:20
COPY --from=deno /deno /usr/local/bin/deno

RUN apt update && apt install -y \
    net-tools \
    procps \
    && rm -rf /var/lib/apt/lists/*

USER node

RUN echo 'alias ll="ls -al"' >> ~/.bash_aliases