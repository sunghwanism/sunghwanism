# Pull an Image and Run a Container

## 1. **Pulling an Image**
Before running a container, you need to pull the desired image from Docker Hub or another registry:
```sh
docker pull [IMAGE_REPOSITORY]:[TAG]
```
Example:
```sh
docker pull ubuntu:latest
```

## **2. Running a Container**
To run a container using the pulled image, use the following command:
```sh
docker run -d --name [CONTAINER_NAME] [IMAGE_REPOSITORY]:[TAG]
```
Example:
```sh
docker run -d --name my_container ubuntu:latest
```
This starts a detached (`-d`) container named `my_container` using the `ubuntu:latest` image.

### Explanation of Common `docker run` Options:
- `-d`: Runs the container in detached mode (in the background). If you want to check its status, use `docker ps`
- `-it`: Runs the container in interactive mode with a terminal
- `-e [ENV_VAR]=[VALUE]`: Sets an environment variable inside the container.
- `--rm`: Automatically removes the container when it exits.
- `-p [HOST_PORT]:[CONTAINER_PORT]`: Maps a port on the host machine to a port inside the container. (To be updated)
- `-v [HOST_PATH]:[CONTAINER_PATH]`: Mounts a directory or volume from the host machine into the container. (To be updated)
- `--network [NETWORK_NAME]`: Connects the container to a specific Docker network. (To be updated)

### Example Usage:
#### Run a container interactively:
```sh
docker run -it --name my_interactive_container ubuntu:latest bash
```
This runs an Ubuntu container and opens an interactive shell (`bash`).

#### Run ad container with network setting
```sh
(To be upadted)
```

---

## 3. **Common Docker Commands**

### Viewing Containers
```bash
docker ps
```
- `-a` : Show all containers, including stopped ones.

### Managing Containers
```bash
# Stop a running container
docker stop [CONTAINER_ID] or [CONTAINER_NAME]

# Start a stopped container
docker start [CONTAINER_ID] or [CONTAINER_NAME]

# Restart a container
docker restart [CONTAINER_ID] or [CONTAINER_NAME]

# Remove a container
docker rm [CONTAINER_ID] or [CONTAINER_NAME]
```

### Viewing Container Logs
```bash
docker logs [CONTAINER_ID] or [CONTAINER_NAME]
```

