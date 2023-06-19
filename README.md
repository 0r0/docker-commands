## Essential Docker Commands Every Developer Should Know
---
It' hard to ignore `docker` this days if you are a Software Developer.
Here I gather the most common docker commands which every developer 
will need in order to do their job better.

---

### ➖Version | [📖 docs](https://docs.docker.com/engine/reference/commandline/version/)
```
docker version
```
To see the Installed Docker version info.

### ➖Search | [📖 docs](https://docs.docker.com/engine/reference/commandline/search/)
```
docker search [name]
```
Search for specefic images on the `Docker Hub`.
For example if you want to get `Neo4j` image run:
```
docker search neo4j
```
### ➖Pull | [📖 docs](https://docs.docker.com/engine/reference/commandline/pull/)
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

### ➖Images | [📖 docs](https://docs.docker.com/engine/reference/commandline/images/)
```
docker images
```
This will print a list of all docker images on the local system.


### ➖Run | [📖 docs](https://docs.docker.com/engine/reference/commandline/run/)
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

### ➖PS
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

