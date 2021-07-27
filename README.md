# TL;DR
**Quickstart On Mac with Docker:**
```
# assumes your current working directory is exploring_geopandas
docker run -d \
           --rm \
           --name jupyter-explore-geopandas \
           -e JUPYTER_ENABLE_LAB=yes \
           -p 8888:8888 \
           -v $PWD:/home/jovyan/work \
           tigerj/jupyter-gis && \
sleep 5 && \
docker logs jupyter-explore-geopandas 2>&1 | grep "http://127.0.0.1" | tail -n 1 | awk '{print $2}'
```

# Usage
Below we will discuss running the `JupyterLab` server.

## Docker
`Docker` will be the primary way discussed for running the `JupyterLab` server.
Please see the [Docker documentation](https://docs.docker.com/get-started/overview/)
for more info about `Docker`.

### Docker Build
To build the `tigerj/jupyter-gis` docker image just execute the following:
```
$ docker build -t tigerj/jupyter-gis github.com/RagingTiger/docker-jupyter-gis
```

### Remove
To remove the server simply stop it
```
$ docker stop jupyter-explore-geopandas
```

### :)
```
head -n 15 README.md
```
