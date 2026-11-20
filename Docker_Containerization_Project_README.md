# Docker & Containerization – Practical Learning Project

## Project Overview

This repository documents a hands-on learning project focused on Docker and containerization. The goal is to understand how applications are packaged, deployed, and run consistently using Docker and Docker Compose.

**Learning workflow:**

`Source Code → Dockerfile → Docker Image → Container → Docker Compose → Running Application`

## Learning Objectives

### 1. Containers and Docker Fundamentals
- Understand containers vs. virtual machines.
- Explore Docker architecture.
- Understand Docker images and containers.
- Learn the purpose and structure of a Dockerfile.
- Apply Dockerfile optimization principles.

### 2. Docker Operations
- Practice essential Docker commands.
- Understand container networking.
- Work with Docker volumes and persistent data.
- Configure applications using environment variables.
- Define and manage multi-container applications with Docker Compose.

### 3. Practical Application Containerization
Build and run a web application through the following stages:

1. Prepare the application source code.
2. Write a Dockerfile.
3. Build a Docker image.
4. Create and run a container.
5. Configure services with Docker Compose.
6. Start the application and test it in a browser.
7. Verify container status, logs, networking, and persistent data.

## Suggested Repository Structure

```text
docker-containerization-project/
├── app/
│   └── (application source code)
├── Dockerfile
├── compose.yaml
├── .dockerignore
├── .env.example
├── README.md
└── screenshots/
    └── (add your own practical screenshots)
```

The exact application files depend on the web application selected for the practical.

## Useful Docker Commands

```bash
# Check Docker version
docker --version

# Display Docker system information
docker info

# Download an image
docker pull nginx:alpine

# List locally available images
docker images

# Run a test container
docker run -d --name web-test -p 8080:80 nginx:alpine

# List running containers
docker ps

# List all containers
docker ps -a

# View container logs
docker logs web-test

# Open a shell inside a running container (if supported by the image)
docker exec -it web-test sh

# Stop and remove the test container
docker stop web-test
docker rm web-test

# Build an image from the current directory
docker build -t my-web-app:1.0 .

# Start services defined in Compose
docker compose up -d --build

# View Compose services
docker compose ps

# Follow service logs
docker compose logs -f

# Stop and remove Compose-managed containers and network
docker compose down
```

## Core Concepts to Document

| Concept | What to explain |
|---|---|
| Container vs VM | Isolation, resource usage, and operating-system model |
| Docker architecture | Docker client, daemon, images, containers, and registry |
| Image | Read-only template used to create containers |
| Container | Running instance created from an image |
| Dockerfile | Instructions used to build an image |
| Networking | How containers communicate with each other and the outside world |
| Volumes | How data can persist beyond a container's lifecycle |
| Environment variables | How configuration is supplied at runtime |
| Docker Compose | How multiple application services are defined and managed |

## Practical Validation Checklist

- [ ] Docker is installed and the Docker service is running.
- [ ] Docker client can communicate with the Docker daemon.
- [ ] A test container starts successfully.
- [ ] A custom image builds successfully from the Dockerfile.
- [ ] The application container starts without errors.
- [ ] The application is reachable at the configured host port.
- [ ] Container logs can be inspected.
- [ ] Container networking works as expected.
- [ ] Persistent data remains available after the relevant container is recreated.
- [ ] Environment variables are applied correctly.
- [ ] Docker Compose starts the required services.
- [ ] `docker compose down` stops the Compose application cleanly.

## Screenshots and Evidence

Add genuine screenshots from your own lab to the `screenshots/` folder. Suggested evidence:

1. Docker version and system information.
2. Docker image list showing the built image.
3. Running container shown by `docker ps`.
4. Dockerfile and Compose configuration.
5. Application successfully opened in a browser.
6. Container logs.
7. Volume or persistent-data verification.
8. Compose services running.

Use clear filenames, for example:

- `01-docker-version.png`
- `02-docker-images.png`
- `03-running-containers.png`
- `04-application-browser.png`
- `05-compose-services.png`

## Security and Good Practices

- Do not commit passwords, API keys, tokens, or real `.env` files.
- Commit `.env.example` with placeholder values only.
- Add `.env` and other sensitive files to `.gitignore`.
- Use trusted, specific image tags rather than relying blindly on `latest`.
- Keep images small by choosing suitable base images and using `.dockerignore`.
- Run containers with only the permissions they need.
- Do not publish container ports unless they need to be accessible.
- Review image contents and dependencies for vulnerabilities.

## Project Outcome

After completing the practical, I should be able to explain the container lifecycle, build an application image, run and inspect containers, manage data and networking, configure an application, and orchestrate services using Docker Compose.

> **Note:** This repository is a learning and documentation template. Update it with the actual application source, configuration, command outputs, screenshots, and observations from your own lab before presenting it as a completed project.
