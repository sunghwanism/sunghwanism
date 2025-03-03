# Writing a Dockerfile
A Dockerfile is a script that defines the environment of a container.

## **Basic Dockerfile Example**
```dockerfile
# Select the base image
FROM ubuntu:18.04

# Update and install required packages
RUN apt-get update && apt-get install -y \
    python3 \
    python3-pip && \
    rm -rf /var/lib/apt/lists/*

# Set the working directory
WORKDIR /app

# Copy all files from the current directory to /app inside the container
COPY . /app

# Define the default command
CMD ["python3", "app.py"]
```

## **Building and Running a Docker Image**
Generate the image using build 
```bash
# Build the Docker image
docker build -t [DOCKERHUB_USERNAME]/[IMAEGENAME]:[TAG] .

# Check the image status
docker images

# Push the Docker image
docker push [DOCKERHUB_USERNAME]/[IMAEGENAME]:[TAG]

# Pull the Docker image
docker pull [DOCKERHUB_USERNAME]/[IMAEGENAME]:[TAG]

# Run the container
docker run -it [DOCKERHUB_USERNAME]/[IMAEGENAME]:[TAG]

# Check the container status
docker ps
```

This setup creates a Docker container that runs `app.py` inside an isolated environment.

---

