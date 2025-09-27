## Technology Stack
- Node.js 24.x (LTS)
- TypeScript
- pnpm (package manager)
- nx (monorepo tooling and build system)
- Jest (testing framework)
- ESLint (code linting)

## Project Structure and Standards

### Package Management
- Use pnpm as the package manager for better performance and disk efficiency
- Install dependencies with `pnpm install`
- Use `pnpm workspace` for monorepo management when applicable
- Lock file: `pnpm-lock.yaml` should be committed to version control

### Build System and Tooling
- Use nx for project orchestration, build caching, and dependency graph management
- Configure nx executors for common tasks (build, test, lint, serve)
- Leverage nx affected commands for efficient CI/CD (`nx affected:build`, `nx affected:test`)
- Use nx generators for consistent project scaffolding

### Code Quality and Formatting
- ESLint configuration should extend recommended TypeScript rules
- Use consistent import ordering and naming conventions
- Implement strict TypeScript configuration (`strict: true`)
- Use absolute imports with path mapping when appropriate

### Testing Standards
- Jest as the primary testing framework
- Organize tests in `__tests__` directories or `.test.ts`/`.spec.ts` files
- Aim for high test coverage with meaningful unit and integration tests
- Use Jest's built-in mocking capabilities for external dependencies
- Configure test environments appropriately (node for backend, jsdom for frontend utilities)

### Development Workflow
- Use semantic versioning for packages
- Implement conventional commits for consistent commit messages
- Configure pre-commit hooks for linting and testing
- Use TypeScript strict mode and resolve all compiler warnings

### Dependencies Management
- Keep dependencies up to date using tools like `pnpm update`
- Use exact versions for critical dependencies
- Separate devDependencies from production dependencies
- Regularly audit for security vulnerabilities with `pnpm audit`