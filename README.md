# .github

Centralized Community Health / Policy Files and Development Templates

---

## Table of Contents

- [Overview](#overview)
- [Available Files](#available-files)
- [How to Use This Repository](#how-to-use-this-repository)
- [Customization](#customization)
- [Contributing](#contributing)
- [Code of Conduct](#code-of-conduct)
- [Security](#security)
- [License](#license)
- [References](#references)

---

## Overview

This repository serves as a **template and reference** for community health files, workflows, and development environment settings that I use across my projects.  
This repo makes it easy to:

- Create new repositories using this one as a template
- Copy standardized policy files into other projects
- Keep consistent configurations across multiple repositories

---

## Available Files

### Community Guidelines

- **[CODE_OF_CONDUCT.md](CODE_OF_CONDUCT.md)** – Standards for community behavior
- **[CONTRIBUTING.md](CONTRIBUTING.md)** – Contribution guidelines, including the DCO
- **[SECURITY.md](SECURITY.md)** – How to responsibly report vulnerabilities

### Configuration Files

- **[LICENSE](LICENSE)** – GNU General Public License v3.0
- **[.editorconfig](.editorconfig)** – Editor consistency rules
- **[.gitignore](.gitignore)** – Common Git ignore patterns
- **[.prettierrc](.prettierrc)** – Prettier formatting configuration
- **[.yamllint](.yamllint)** – YAML linting rules
- **[markdownlint-cli2.jsonc](markdownlint-cli2.jsonc)** – Markdown linting configuration

### GitHub Workflows (`.github/workflows/`)

- **lint-files.yml** – Lints files on push and pull requests
- **close-stale.yml** – Automatically closes stale issues and PRs

### Development Environment (`.devcontainer/`)

A ready-to-use development environment including:

- hadolint, shellcheck, yamllint, markdownlint
- Preconfigured VS Code settings and recommended extensions

---

## How to Use This Repository

### Option 1: Create a New Repository From This Template

This repository is configured as a template. To create a new project based on it:

1. Click **“Use this template”** on GitHub
2. Choose a repository name
3. Customize as needed

This includes all workflows, policies, configs, and devcontainer settings.

### Option 2: Copy Specific Files Into an Existing Repository

If you want only a subset of these files:

1. Copy the desired files into your project
2. Commit them normally
3. Adjust them to fit your needs

### Option 3: Reuse the Dev Container

```bash
# Copy the devcontainer into your project
cp -r .devcontainer /path/to/your/repository/

# Open the repository in VS Code and select “Reopen in Container”
```

### Option 4: Use the CI/CD Workflows

To use the CI/CD workflows in your project:

```bash
# Create workflows directory if it doesn't exist
mkdir -p .github/workflows

# Copy the workflows you want to use
cp .github/workflows/lint-files.yml /path/to/your/repository/.github/workflows/
cp .github/workflows/close-stale.yml /path/to/your/repository/.github/workflows/
```

You may need to adjust workflow permissions in your repository settings.

---

## Customization

### Linting Configuration

The following linters are configured and can be customized:

- **Hadolint** – Dockerfile linting (config in `.vscode/settings.json`)
- **ShellCheck** – Shell script linting
- **yamllint** – YAML linting (config in `.yamllint`)
- **markdownlint** – Markdown linting (config in `markdownlint-cli2.jsonc`)

### VS Code Settings

Editor-specific settings are provided in `.vscode/settings.json`, including:

- Format-on-save options
- Linter integrations
- Formatter choices (Prettier, shell-format, Docker)

---

## Contributing

If you would like to contribute to this project, please see **[CONTRIBUTING.md](CONTRIBUTING.md)**.

Before submitting a PR, you may test your code using Super-Linter:

```bash
docker run --rm \
           -e ACTIONS_RUNNER_DEBUG=true \
           -e RUN_LOCAL=true \
           -e DEFAULT_BRANCH=main \
           --env-file ".github/super-linter.env" \
           -v "$PWD":/tmp/lint \
           ghcr.io/super-linter/super-linter:latest
```

---

## Code of Conduct

See **[CODE_OF_CONDUCT.md](CODE_OF_CONDUCT.md)** for community standards.

---

## Security

See **[SECURITY.md](SECURITY.md)** for vulnerability reporting instructions.

---

## License

Copyright Universidade Federal do Espirito Santo (Ufes)

This program is free software: you can redistribute it and/or modify
it under the terms of the GNU General Public License as published by
the Free Software Foundation, either version 3 of the License, or
(at your option) any later version.

This program is distributed in the hope that it will be useful,
but WITHOUT ANY WARRANTY; without even the implied warranty of
MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE. See the
GNU General Public License for more details.

You should have received a copy of the GNU General Public License
along with this program. If not, see <https://www.gnu.org/licenses/>.

This program is released under license GNU GPL v3+ license.

---

## References

- [GitHub Community Health Files Documentation](https://docs.github.com/en/communities/setting-up-your-project-for-healthy-contributions/creating-a-default-community-health-file)
- [Dev Containers Specification](https://containers.dev/)
- [GitHub Actions Documentation](https://docs.github.com/en/actions)
