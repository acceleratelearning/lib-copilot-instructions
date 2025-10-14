## Instructions for Building Containers

- Containers should be built to be read only and to run as a non-root user
- Docker compose should be used for local testing, but the container will run in a Kubernetes cluster
- The docker compose `version` attribute is deprecated and should not be included in `docker-compose.yaml` or `docker-compose.yml` files
- Deployment of the container is not a concern for this repository.  Deployment will be handled with a different repository that uses ArgoCD
- Secrets should be created using docker secrets and made available as environment variables.
- For local development, an .env file will be used to provider secrets to docker compose
- Docker compose should support local development with hot reload
