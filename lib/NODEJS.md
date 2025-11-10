## Instructions for Building Containers

- Containers should be built to be read only and to run as a non-root user
- Dockerfiles should specify the latest syntax version
- When executing multiple commands in a Docker RUN command, use the HEREDOC syntax instead of chaining commands with &&
- Docker compose should be used for local testing, but the container will run in a Kubernetes cluster
- The docker compose `version` attribute is deprecated and should not be included in `docker-compose.yaml` or `docker-compose.yml` files
- Deployment of the container is not a concern for this repository. Deployment will be handled with a different repository that uses ArgoCD
- Secrets should be created using docker secrets and made available as environment variables.
- For local development, an .env file will be used to provider secrets to docker compose
- Docker compose should support local development with hot reload

## Building, Testing, and Linting

### Prerequisites
Before running any commands, ensure dependencies are installed:
```bash
corepack enable
pnpm install
```

### Available Commands

**Build all projects:**
```bash
pnpm exec nx run-many -t build
```

**Run tests:**
```bash
pnpm exec nx run-many -t test
```

**Lint code:**
```bash
pnpm exec nx run-many -t lint
```

**Type check:**
```bash
pnpm exec nx run-many -t typecheck
```

**Format code:**
```bash
pnpm exec nx run-many -t format
```

**Run all checks (format, lint, test, build, typecheck):**
```bash
pnpm run all
```

### Working with Individual Projects

To target a specific project, use:
```bash
pnpm exec nx run <project-name>:<target>
```

Example:
```bash
pnpm exec nx run @ali-platform/testy-mc-test-service:test
```

### Running Affected Projects Only

Use Nx's affected commands to run tasks only on projects affected by your changes:
```bash
pnpm exec nx affected -t test
pnpm exec nx affected -t build
```

## Testing Standards

- All new features should include appropriate unit tests
- Tests should be placed alongside the code they test (e.g., `app.spec.ts` next to `app.ts`)
- Use Jest for unit testing
- Use Playwright for end-to-end testing
- Tests must pass before code is merged
- Aim for meaningful test coverage, not just high percentages

## Files and Directories to Avoid Modifying

- Do not modify `.github/workflows/repository-maintenance.yaml` - this is managed externally
- Build artifacts in `dist/`, `tmp/`, `.next/`, `out/` are gitignored and should not be committed
- Do not modify `pnpm-lock.yaml` directly - use `pnpm install` or `pnpm update` commands
- The `.nx/cache` directory is for Nx's internal use only