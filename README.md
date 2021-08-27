# PYTHON ENVIRONMENT BUILDER - REPOSITORY <h1> 
 
[![build](https://img.shields.io/github/workflow/status/lyscm/environments-python/environment-python%20-%20ci?logo=github)](https://github.com/lyscm/environments-python/blob/master/.github/workflows/build-action.yml)
[![repo size](https://img.shields.io/github/repo-size/lyscm/environments-python?logo=github)](https://github.com/lyscm/environments-python)
[![package](https://img.shields.io/static/v1?label=package&message=python&color=yellowgreen&logo=github)](https://github.com/lyscm/environments-python/pkgs/container/environments%2Fpython)

## Initiate package(s): <h2> 

Set parameters:

***Bash:***
```bash
OWNER=lyscm
CONTAINER_NAME=python
TAG=ghcr.io/lyscm/environments/python
```

***Powershell:***
```powershell
$OWNER="lyscm"
$CONTAINER_NAME="python"
$TAG="ghcr.io/lyscm/environments/python"
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
    --privileged \
    $TAG
```