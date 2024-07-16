# Docker Nginx App with OPA Verification

This project demonstrates a simple Docker application using Nginx to serve a "Hello World" page, with deployment verification using Open Policy Agent (OPA).

## Prerequisites

- Docker
- OPA CLI

## Quick Start

The OPA rules are located at sc-policy-repo.

1. Build the Docker image:
docker build -t nginx-hello-world .
2. Run the OPA verification:
opa eval --format pretty --data deploy.rego --input Dockerfile "data.deploy.allow"
3. If the OPA check passes, run the container:
docker run -d -p 8080:80 nginx-hello-world
4. Access the application at `http://localhost:8080`
