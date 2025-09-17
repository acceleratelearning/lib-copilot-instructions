## Instructions for Container

- Containers should be built to be read only and to run as a non-root user
- Docker compose should be used for local testing, but the container will run in a Kubernetes cluster
- Deployment of the container is not a concern for this repository.  Deployment will be handled with a different repository that uses ArgoCD
- Secrets should be delivered using environment variables.  For local development, an .env file will be used to provider secrets to docker compose
