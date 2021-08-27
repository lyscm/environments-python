# PYTHON ENVIRONMENT BUILDER - REPOSITORY <h1> 

[![environments-python - CI](https://github.com/lyscm/environments-python/actions/workflows/deploy-packages.yml/badge.svg?branch=master)](https://github.com/lyscm/environments-python/actions/workflows/deploy-packages.yml)

## Initiate package(s): <h2> 

Set parameters:

```bash
OWNER=lyscm
CONTAINER_NAME=python
TAG=ghcr.io/lyscm/environments/python
```
Remove any existing container:

```bash
docker stop $CONTAINER_NAME
docker rm $CONTAINER_NAME
docker pull $TAG
```

Run container:

```bash
docker run \
    -d \
    --name $CONTAINER_NAME \
    --restart unless-stopped \
    -v /var/run/docker.sock:/var/run/docker-host.sock \
    --net=host \
    --cap-add=SYS_PTRACE \
    --security-opt seccomp:unconfined \
    --privileged \
    $TAG
```