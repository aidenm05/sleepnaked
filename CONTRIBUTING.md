# Contributing to Sleep Naked

Thank you for your interest in contributing to Sleep Naked! We welcome contributions from the community and are excited to work together to build a better sleep experience.

## Getting Started

1. **Fork the repository** on GitHub.
2. **Clone your fork** locally:
   ```bash
   git clone https://github.com/YOUR_USERNAME/sleepnaked.git
   cd sleepnaked
   ```
3. **Create a feature branch** from `main`:
   ```bash
   git checkout -b feature/your-feature-name
   ```

## How to Contribute

### Reporting Bugs

- Check existing [issues](https://github.com/aidenm05/sleepnaked/issues) before opening a new one.
- Provide a clear title and description.
- Include steps to reproduce, expected behavior, and actual behavior.
- Add relevant screenshots or logs if applicable.

### Suggesting Features

- Open an issue with the label `enhancement`.
- Describe the feature, its motivation, and potential implementation approach.

### Submitting Code Changes

1. Ensure your code follows the project's coding style.
2. Write or update tests for any changed functionality.
3. Run the full test suite to confirm nothing is broken.
4. Commit your changes with clear, descriptive commit messages.
5. Push your branch and open a **Pull Request** against `main`.
6. Fill in the pull request template, linking any related issues.

## Code Style

- Follow language-specific conventions for each part of the project (see `docs/architecture.md`).
- Keep functions small and focused.
- Document public APIs and complex logic with comments.

## Branching Strategy

| Branch | Purpose |
|--------|---------|
| `main` | Stable production-ready code |
| `develop` | Integration branch for features |
| `feature/*` | Individual feature work |
| `bugfix/*` | Bug fix branches |
| `hotfix/*` | Urgent production fixes |

## Commit Message Guidelines

Use the [Conventional Commits](https://www.conventionalcommits.org/) format:

```
<type>(<scope>): <short summary>

[optional body]
[optional footer]
```

**Types:** `feat`, `fix`, `docs`, `style`, `refactor`, `test`, `chore`

**Example:**
```
feat(mobile): add sleep tracking screen
fix(backend): correct sleep score calculation
docs(api): update endpoint documentation
```

## Code of Conduct

Please read and follow our [Code of Conduct](CODE_OF_CONDUCT.md). We are committed to making participation in this project a harassment-free experience for everyone.

## Questions?

Feel free to open an issue or reach out to the maintainers. We're happy to help!
