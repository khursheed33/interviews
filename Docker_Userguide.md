# Docker and Docker Compose Guide

## Table of Contents

1. [Introduction](#introduction)
2. [Dockerfile](#dockerfile)
   - [Example 1: Simple Python Application](#example-1-simple-python-application)
   - [Example 2: Multi-stage Build](#example-2-multi-stage-build)
3. [Docker Compose](#docker-compose)
   - [Example 1: Simple Web Application](#example-1-simple-web-application)
   - [Example 2: Multi-container Application](#example-2-multi-container-application)
4. [Docker Container Management](#docker-container-management)
   - [Copying Files to a Container](#copying-files-to-a-container)
   - [Exploring a Container](#exploring-a-container)
5. [Docker Networking](#docker-networking)
6. [Docker Volumes](#docker-volumes)
7. [Credentials Management](#credentials-management)
8. [Additional Tips and Commands](#additional-tips-and-commands)

## Introduction

Docker is a platform for developing, shipping, and running applications inside containers. Containers allow a developer to package up an application with all parts it needs, such as libraries and other dependencies, and ship it all out as one package.

Docker Compose is a tool for defining and running multi-container Docker applications. With Compose, you use a YAML file to configure your application’s services. Then, with a single command, you create and start all the services from your configuration.

## Dockerfile

A Dockerfile is a text document that contains all the commands a user could call on the command line to assemble an image.

### Example 1: Simple Python Application

```dockerfile
# Use the official Python image from the Docker Hub
FROM python:3.8-slim

# Set the working directory in the container
WORKDIR /app

# Copy the current directory contents into the container at /app
COPY . /app

# Install any needed packages specified in requirements.txt
RUN pip install --no-cache-dir -r requirements.txt

# Make port 80 available to the world outside this container
EXPOSE 80

# Define environment variable
ENV NAME World

# Run app.py when the container launches
CMD ["python", "app.py"]
```

### Example 2: Multi-stage Build

```dockerfile
# Stage 1: Build
FROM golang:1.16 as builder

WORKDIR /app
COPY . .

RUN go mod download
RUN go build -o myapp .

# Stage 2: Run
FROM alpine:latest

WORKDIR /root/
COPY --from=builder /app/myapp .

CMD ["./myapp"]
```

## Docker Compose

Docker Compose allows you to define and manage multi-container Docker applications.

### Example 1: Simple Web Application

**docker-compose.yml**

```yaml
version: '3'
services:
  web:
    image: nginx
    ports:
      - "80:80"
```

### Example 2: Multi-container Application

**docker-compose.yml**

```yaml
version: '3'
services:
  web:
    image: my_web_app:latest
    build: .
    ports:
      - "5000:5000"
    depends_on:
      - db
  db:
    image: postgres:13
    environment:
      POSTGRES_USER: example
      POSTGRES_PASSWORD: example
      POSTGRES_DB: example_db
```

## Docker Container Management

### Copying Files to a Container

```sh
docker cp local_file_path container_name:/container_path
```

### Exploring a Container

```sh
# Start a bash session in a running container
docker exec -it container_name bash

# View logs from a container
docker logs container_name
```

## Docker Networking

Docker creates a default network for your containers to communicate. You can create custom networks:

```sh
# Create a new network
docker network create my_network

# Connect a container to the network
docker network connect my_network container_name

# List networks
docker network ls
```

## Docker Volumes

Volumes are the preferred mechanism for persisting data generated and used by Docker containers.

```sh
# Create a volume
docker volume create my_volume

# Use a volume in a container
docker run -d -v my_volume:/data my_image

# List volumes
docker volume ls
```

**docker-compose.yml with volumes**

```yaml
version: '3'
services:
  db:
    image: postgres:13
    volumes:
      - db_data:/var/lib/postgresql/data
volumes:
  db_data:
```

## Credentials Management

Manage sensitive data using Docker secrets (available in Swarm mode) or environment variables.

```yaml
version: '3.7'
services:
  db:
    image: mysql:5.7
    environment:
      MYSQL_ROOT_PASSWORD: ${MYSQL_ROOT_PASSWORD}
```

**.env file**

```
MYSQL_ROOT_PASSWORD=example_password
```

## Additional Tips and Commands

### Basic Docker Commands

```sh
# Build an image from a Dockerfile
docker build -t my_image .

# Run a container
docker run -d -p 80:80 my_image

# List all running containers
docker ps

# Stop a running container
docker stop container_name

# Remove a container
docker rm container_name

# Remove an image
docker rmi image_name
```

### Docker Compose Commands

```sh
# Start services defined in docker-compose.yml
docker-compose up

# Start services in the background
docker-compose up -d

# Stop services
docker-compose down

# View logs
docker-compose logs

# Scale services
docker-compose up -d --scale web=3
```
