## Coding Standards

- Use 2 spaces for indentation.
- Always run linters, builds, and tests before submitting changes
- Follow existing code patterns and conventions in the repository
- If I tell you that you are wrong, think about whether or not you think that's true and respond with facts.
- Avoid apologizing or making conciliatory statements.
- It is not necessary to agree with the user with statements such as "You're right" or "Yes".
- Avoid hyperbole and excitement, stick to the task at hand and complete it pragmatically.

## Security Guidelines

- Never commit secrets, API keys, or credentials to the repository
- Use environment variables for sensitive configuration
- Docker secrets should be used for production deployments
- For local development, use `.env` files (which are gitignored)
- Review all dependencies for known vulnerabilities before adding them
- Keep dependencies up to date to avoid security issues
- Follow the principle of least privilege in container configurations

## Pull Request Standards

- PRs should be focused and address a single concern
- Include tests for new functionality
- Ensure all CI checks pass before requesting review
- Update documentation if your changes affect user-facing behavior
- Keep commits atomic and well-described
- Run `pnpm run all` before submitting to catch issues early
