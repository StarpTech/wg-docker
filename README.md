[![Tests](https://github.com/wundergraph/docker/actions/workflows/ci.yml/badge.svg)](https://github.com/wundergraph/docker/actions/workflows/ci.yml)

# Docker

This repository instructs you how to build a docker container for WunderGraph. It's aligned with [best practices](https://github.com/nodejs/docker-node/blob/main/docs/BestPractices.md) of the community.

Trigger 108

> **Note**: The approach used in this repository assumes that you build your dependencies inside docker. While this a good practice, it's not always practical. For example, if you want to take advantage of the CI cache you need to modify the dockerfile accordingly.

## Example

```
.
└── app/
    ├── .wundergraph/
    │   ├── generated/
    │   ├── operations/
    │   ├── wundergraph.config.ts
    │   ├── wundergraph.server.ts
    │   └── wundergraph.operations.ts
    ├── Dockerfile
    ├── .dockerignore
    ├── tsconfig.json
    └── package.json
```

### Test

```shell
# Install your project to generate a lockfile
npm i
# Build the docker image
docker build -t wundergraph .
```

Run `docker run -p 9991:9991 wundergraph:latest` to test your image.