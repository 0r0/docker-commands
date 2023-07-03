## Essential Docker Commands Every Developer Should Know
---
It' hard to ignore `docker` this days if you are a Software Developer.
Here I gather the most common docker commands which every developer 
will need in order to do their job better.

---

### ⭕️ Version | [📖 docs](https://docs.docker.com/engine/reference/commandline/version/)
```
docker version
```
To see the Installed Docker version info.

### ⭕️ Search | [📖 docs](https://docs.docker.com/engine/reference/commandline/search/)
```
docker search [name]
```
Search for specefic images on the `Docker Hub`.
For example if you want to get `Neo4j` image run:
```
docker search neo4j
```
### ⭕️ Pull | [📖 docs](https://docs.docker.com/engine/reference/commandline/pull/)
```
docker pull [name]:[TAG]
```
Pull an image from the `Docker Hub`
- `[name]` is the name for the image. ex: `neo4j`
- `[TAG]` you can sepecify which version of the image you want to pull. If not specified, the `latest` tag will be used by default.
- `--platform` set this option to pull image for the specified platform and OS
- `-a` or `--all-tags` to pull all available tags from the registry
- `-q` or `--quiet` to suppress verbose output
  
**Examples:**
```
docker pull neo4j
```
this will pull the latest official image for `Neo4j`.
```
docker pull --all-tags ubuntu
```
this will pull all images from `ubuntu` repository.
```
docker pull ubuntu:22.04
```
this will pull a specefic version of `ubuntu`.

### ⭕️ Images | [📖 docs](https://docs.docker.com/engine/reference/commandline/images/)
```
docker images
```
This will print a list of all docker images on the local system.


### ⭕️ Run | [📖 docs](https://docs.docker.com/engine/reference/commandline/run/)
```
docker run [name] [command] [args]
```
Creates and run a new container from an image.

**Examples:**
```
docker run neo4j
```
simply runs the `neo4j` image in a new container
```
docker run --name test -it neo4j
```
run a container named `test` form `neo4j` image

### ⭕️ PS | [📖 docs](https://docs.docker.com/engine/reference/commandline/ps/)
```
docker ps 
```
Lists docker running containers.
**Examples:**
```
docker ps --all
```
`--all` or `-a` list all containers. default just shows running.
```
docker ps --latest
```
`--latest` or `-l` list the latest created container

### ⭕️ Restart | [📖 docs](https://docs.docker.com/engine/reference/commandline/restart/)
```
docker restart [CONTAINER]
```
restart one or more container.

### ⭕️ Kill | [📖 docs](https://docs.docker.com/engine/reference/commandline/kill/)
```
docker kill [CONTAINER]
```
Kill one or more containers
**Examples:**
```
docker kill neo4j_imun postgress-UX59
```
This will kill these 2 containers.


### ⭕️ Stop | [📖 docs](https://docs.docker.com/engine/reference/commandline/stop/)
```
docker stop [CONTAINER]
```
Stop one or more containers.
```
docker stop -t 10000 Neo4j-98xt
```
Stops Neo4j container after waiting for a specific time.

### ⭕️ Build | [📖 docs](https://docs.docker.com/engine/reference/commandline/build/)
```
docker build [DockerFilePath]
```
Build an image from a docker file or docker repository.

### ⭕️ Attach | [📖 docs](https://docs.docker.com/engine/reference/commandline/attach/)
```
docker attach [CONTAINER]
```
Attach your terminal to a running container to control I/O operations.

### ⭕️ Exec | [📖 docs](https://docs.docker.com/engine/reference/commandline/exec/)
```
docker exec [CONTAINER] [COMMANDS]
```
Executes cli commands in a running container.
```
docker exec ubuntu-76sx touch /tmp/myfile
```
This will creates a file in `ubuntu-76sx` container.
```
docker exec -it ubuntu-76sx sh
```
This starts a new shell session in the `ubuntu-76sx` container.

### ⭕️ Logs | [📖 docs](https://docs.docker.com/engine/reference/commandline/logs/)
```
docker logs [CONTAINER]
```
See the logs for a given container.
```
docker logs --follow ubuntu-76sx
```
Use `--follow` or `-f` for display logs of `ubuntu-76sx` container and follow the output as the logs continues.
```
docker logs -f --until=30m neo4j-ex54
```
this will display logs before a specific point in time.

### ⭕️ Commit | [📖 docs](https://docs.docker.com/engine/reference/commandline/commit/)
```
docker commit [CONTAINER] [REPOSITORY]
```
Create a new image from a container's changes. The new image will not include any data from the container's volumes.
```
docker commit neo4j-es87 example/test:v4
```
This will creates a new image from `neo4j-es87` container in `example/test` repository with `v4` as its tag.
You can use `--change` options to apply dockerfile instructions to the new image being created.

---

