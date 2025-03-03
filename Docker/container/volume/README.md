
# Docker Volumes

## What are Volumes?
Volumes are the primary mechanism for persisting data generated and used by Docker containers. If a container is run without explicitly creating a volume, Docker automatically creates a directory with a hash-based name. However, if a volume is created beforehand and specified when running a container, the directory is created using the assigned volume name.

## Bind Mount

### Bind Mount between local and container
To mount a created volume when running a container, use the `-v` option:
```sh
docker run -d --name [CONTAINER_NAME] -v [VOLUME_NAME]:/[CONTAINER_DIR] [IMAGE_REPOSITORY]:[TAG]
```

### Example:
```sh
# Create a volume named 'my_volume'
docker volume create my_volume

# Run a container and mount 'my_volume' to '/app' in the container
docker run -d --name my_container -v my_volume:/app ubuntu:latest
```

This ensures that data written to `/app` in the container persists even if the container is removed.

---

## Docker Container Default Volume Setting