# Docker Deployment

## Overview

In this laboratory activity, I used the KillerCoda Ubuntu Playground to practice basic Docker commands and deploy an Nginx web server inside a container. The activity demonstrated how containers can be pulled, started, accessed through a mapped port, stopped, and removed.

## Checkpoint 3 — Verify Docker

I first checked whether Docker was installed by running:

```bash
docker --version
```

I then checked the Docker environment with:

```bash
docker info
```

The `docker --version` command displays the installed Docker version, while `docker info` provides information about the Docker environment and daemon.

**Evidence:** `screenshots/docker-version.png`

## Checkpoint 4 — Deploy Nginx

### Pull the Nginx Image

I downloaded the official Nginx image using:

```bash
docker pull nginx
```

### Run the Nginx Container

I started the Nginx web server in detached mode and mapped host port 8080 to container port 80:

```bash
docker run -d -p 8080:80 --name nginx-server nginx
```

The `-d` option runs the container in the background.

The `-p 8080:80` option maps port 8080 on the host machine to port 80 inside the Nginx container.

The `--name nginx-server` option gives the container a readable name.

### Test the Web Server

I tested the Nginx server using:

```bash
curl http://localhost:8080
```

A successful request displays the HTML response from the Nginx welcome page.

**Evidence:** `screenshots/nginx-running.png`

## Checkpoint 5 — Container Lifecycle

### 1. List Running Containers

```bash
docker ps
```

This command displays the containers that are currently running.

### 2. Stop the Container

```bash
docker stop nginx-server
```

This command stops the running Nginx container.

### 3. Verify the Container Is Stopped

```bash
docker ps
```

After stopping the container, it should no longer appear in the list of running containers.

To also display stopped containers, I can use:

```bash
docker ps -a
```

### 4. Remove the Container

```bash
docker rm nginx-server
```

This command permanently removes the stopped Nginx container from the Docker environment.

**Evidence:** `screenshots/container-lifecycle.png`

## Port Mapping

The port mapping:

```text
8080:80
```

means that requests sent to port 8080 on the host are forwarded to port 80 inside the Nginx container. Nginx normally listens for HTTP traffic on port 80 inside the container, while port 8080 provides an accessible port on the host.

## Result

The Nginx web server was successfully deployed as a Docker container. I was able to verify the server using `curl`, manage the container through the Docker lifecycle commands, and finally remove the container from the environment.
