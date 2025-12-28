# Contributing to TAURUS AI Projects

Thank you for your interest in contributing to TAURUS AI Corp projects! We welcome contributions from the community and are grateful for your support.

## Table of Contents

- [Code of Conduct](#code-of-conduct)
- [Contributor License Agreement](#contributor-license-agreement)
- [Getting Started](#getting-started)
- [How to Contribute](#how-to-contribute)
- [Development Setup](#development-setup)
- [Pull Request Process](#pull-request-process)
- [Style Guidelines](#style-guidelines)
- [Community](#community)

---

## Code of Conduct

This project adheres to the [Contributor Covenant Code of Conduct](CODE_OF_CONDUCT.md). By participating, you are expected to uphold this code. Please report unacceptable behavior to conduct@taurusai.io.

---

## Contributor License Agreement

Before we can accept your contributions, you must sign our Contributor License Agreement (CLA):

- **Individual Contributors**: Please review and sign the [Individual CLA](CLA.md)
- **Corporate Contributors**: Please review and sign the [Corporate CLA](CCLA.md)

### Why a CLA?

The CLA protects both you and TAURUS AI Corp:
- Confirms you have the right to contribute your code
- Grants us the necessary rights to use and distribute your contributions
- Ensures our projects can be used by everyone under our Triple-Plus License

---

## Getting Started

### Prerequisites

Depending on the project, you may need:

- **Node.js 20+** (for TypeScript/JavaScript projects)
- **Python 3.12+** (for Python projects)
- **Docker** (for containerized development)
- **Git** (for version control)

### Finding Issues to Work On

1. Look for issues labeled `good first issue` for beginner-friendly tasks
2. Check `help wanted` labels for issues where we need community help
3. Browse our [project boards](https://github.com/orgs/Taurus-Ai-Corp/projects) for current priorities

---

## How to Contribute

### Reporting Bugs

1. Check if the bug has already been reported in [Issues](https://github.com/Taurus-Ai-Corp/.github/issues)
2. If not, create a new issue using our [Bug Report template](.github/ISSUE_TEMPLATE/bug_report.yml)
3. Include as much detail as possible: steps to reproduce, expected behavior, screenshots

### Suggesting Features

1. Check existing [feature requests](https://github.com/Taurus-Ai-Corp/.github/issues?q=is%3Aissue+label%3Aenhancement)
2. Create a new issue using our [Feature Request template](.github/ISSUE_TEMPLATE/feature_request.yml)
3. Explain the use case and benefits clearly

### Submitting Code

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/amazing-feature`)
3. Make your changes
4. Write or update tests as needed
5. Commit your changes (see [Commit Guidelines](#commit-guidelines))
6. Push to your fork (`git push origin feature/amazing-feature`)
7. Open a Pull Request

---

## Development Setup

### TypeScript/JavaScript Projects

```bash
# Clone the repository
git clone https://github.com/Taurus-Ai-Corp/[project-name].git
cd [project-name]

# Install dependencies
npm install

# Run development server
npm run dev

# Run tests
npm test

# Run linting
npm run lint
```

### Python Projects

```bash
# Clone the repository
git clone https://github.com/Taurus-Ai-Corp/[project-name].git
cd [project-name]

# Create virtual environment
python -m venv venv
source venv/bin/activate  # On Windows: venv\Scripts\activate

# Install dependencies
pip install -r requirements.txt

# Run tests
pytest

# Run linting
flake8 .
```

---

## Pull Request Process

### Before Submitting

- [ ] Sign the CLA (required for all contributions)
- [ ] Update documentation if needed
- [ ] Add tests for new functionality
- [ ] Ensure all tests pass locally
- [ ] Run linting and fix any issues
- [ ] Update CHANGELOG.md if applicable

### PR Requirements

1. **Title**: Use a clear, descriptive title
2. **Description**: Explain what changes you made and why
3. **Issue Link**: Reference any related issues (`Fixes #123`)
4. **Tests**: Include tests for new functionality
5. **Documentation**: Update docs if behavior changes

### Review Process

1. A maintainer will review your PR within 3-5 business days
2. Address any requested changes
3. Once approved, a maintainer will merge your PR
4. Your contribution will be included in the next release

### Priority Support for Sponsors

[Bronze+ sponsors](SPONSORS.md) receive priority PR reviews with a 24-hour response SLA.

---

## Style Guidelines

### Commit Guidelines

We follow [Conventional Commits](https://www.conventionalcommits.org/):

```
type(scope): description

[optional body]

[optional footer]
```

**Types:**
- `feat`: New feature
- `fix`: Bug fix
- `docs`: Documentation only
- `style`: Code style (formatting, etc.)
- `refactor`: Code refactoring
- `test`: Adding/updating tests
- `chore`: Maintenance tasks

**Examples:**
```
feat(auth): add quantum-resistant signature verification
fix(api): resolve token expiration issue
docs(readme): update installation instructions
```

### Code Style

- **TypeScript/JavaScript**: ESLint + Prettier configuration in each project
- **Python**: PEP 8 with Black formatter
- **Commit Messages**: Conventional Commits format
- **Documentation**: Markdown with clear examples

---

## Community

### Get Help

- **Discord**: [Join our community](https://discord.gg/taurusai)
- **Discussions**: [GitHub Discussions](https://github.com/orgs/Taurus-Ai-Corp/discussions)
- **Email**: support@taurusai.io

### Stay Updated

- Watch repositories you're interested in
- Join our Discord for announcements
- Follow [@TaurusAICorp](https://twitter.com/TaurusAICorp) on Twitter

---

## Recognition

All contributors are recognized in our:
- Repository CONTRIBUTORS.md file
- Release notes
- Annual contributor spotlight

[Sponsors](SPONSORS.md) receive additional recognition based on their tier.

---

## Questions?

If you have questions about contributing, please:
1. Check our [FAQ](https://taurusai.io/faq)
2. Ask in [Discord](https://discord.gg/taurusai)
3. Email contribute@taurusai.io

Thank you for contributing to TAURUS AI!
