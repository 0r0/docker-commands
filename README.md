## Essential Docker Commands Every Developer Should Know
---
It' hard to ignore `docker` this days if you are a Software Developer.
Here I gather the most common docker commands which every developer 
will need in order to do their job better.

---

### Version
```
docker version
```
To see the Installed Docker version info.

### Search
```
docker search [name]
```
Search for specefic images on the `Docker Hub`.
For example if you want to get `Neo4j` image run:
```
docker search neo4j
```
### Pull
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

###
