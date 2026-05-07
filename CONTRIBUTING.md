# Contributing to Leshine

We appreciate your interest in contributing to Leshine! This document provides guidelines and instructions for contributing.

## Code of Conduct

Please be respectful and professional in all interactions.

## Getting Started

1. Fork the repository
2. Clone your fork: `git clone https://github.com/YOUR_USERNAME/leshine.git`
3. Create a virtual environment: `python -m venv venv`
4. Activate it: `source venv/bin/activate` (or `venv\Scripts\activate` on Windows)
5. Install dependencies: `pip install -r requirements.txt`
6. Create a feature branch: `git checkout -b feature/your-feature`

## Development Workflow

1. Make your changes
2. Write or update tests
3. Run tests: `pytest`
4. Run linting: `flake8 .`
5. Format code: `black .`
6. Commit with clear messages: `git commit -m "Add feature description"`
7. Push to your fork: `git push origin feature/your-feature`
8. Open a Pull Request

## Pull Request Guidelines

- Provide a clear description of changes
- Reference related issues
- Include tests for new features
- Update documentation as needed
- Ensure code follows PEP 8 standards
- Add yourself to CONTRIBUTORS.md

## Testing

Run all tests:
```bash
pytest
```

Run with coverage:
```bash
pytest --cov=leshine
```

Run specific test:
```bash
pytest tests/test_markets.py::test_create_market
```

## Code Style

We follow PEP 8 and use:
- `black` for code formatting
- `flake8` for linting
- `isort` for import sorting

```bash
black .
flake8 .
isort .
```

## Commit Messages

Use clear, descriptive commit messages:
- ✅ `Add KYC verification endpoint`
- ✅ `Fix portfolio calculation bug`
- ✅ `Update market API documentation`
- ❌ `fix bug`
- ❌ `update stuff`

## Issues

- Use GitHub issues for bug reports and feature requests
- Check existing issues before creating new ones
- Include reproduction steps for bugs
- Provide context and expected behavior

## Questions?

Open a GitHub issue or contact us at support@leshine.com

Thanks for contributing! 🚀
