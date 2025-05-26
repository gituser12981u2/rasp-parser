# Contributing to RASP Parser

Thank you for your interest in contributing to RASP Parser. This document provides guidelines for contributing to the project.

## Development Setup

1. **Fork and clone the repository:**

   ```bash
   git clone https://github.com/gituser12981u2/rasp-parser.git
   cd rasp-parser
   ```

2. **Create a virtual environment:**

   ```bash
   python -m venv venv
   source venv/bin/activate  # On Windows: venv\Scripts\activate
   ```

3. **Install development dependencies:**

   ```bash
   pip install -e .[dev,scipy]
   ```

## Code Style

- **Formatting:** Use `black` for code formatting
- **Linting:** Use `flake8` for linting
- **Type hints:** Use type hints throughout (checked with `mypy`)
- **Line length:** Maximum 88 characters

```bash
# Format code
black rasp_parser tests

# Lint code
flake8 rasp_parser tests

# Type check
mypy rasp_parser
```

## Testing

- Write tests for all new functionality
- Ensure all tests pass before submitting PR
- Aim for high test coverage

```bash
# Run tests
pytest

# Run with coverage
pytest --cov=rasp_parser --cov-report=term-missing
```

## Submitting Changes

1. **Create a feature branch:**

   ```bash
   git checkout -b feature/your-feature-name
   ```

2. **Make your changes:**
   - Write clean, well-documented code
   - Add tests for new functionality
   - Update documentation if needed

3. **Test your changes:**

   ```bash
   pytest
   black rasp_parser tests
   flake8 rasp_parser tests
   mypy rasp_parser
   ```

4. **Commit and push:**

   ```bash
   git add .
   git commit -m "Add feature: description of your changes"
   git push origin feature/your-feature-name
   ```

5. **Create a Pull Request:**
   - Use a clear, descriptive title
   - Explain what changes you made and why
   - Reference any related issues

## Code Organization

- **`rasp_parser/models.py`:** Data structures and calculations
- **`rasp_parser/core.py`:** Parsing logic
- **`rasp_parser/validation.py`:** Data validation
- **`rasp_parser/exceptions.py`:** Custom exceptions
- **`tests/`:** Test files (mirror the package structure)

## Adding New Features

When adding new features:

1. **Consider backward compatibility**
2. **Add appropriate error handling**
3. **Write comprehensive tests**
4. **Update documentation**
5. **Follow existing code patterns**

## Integration Methods

If you're improving integration accuracy:

- Maintain the fallback hierarchy: cubic spline → Simpson's → trapezoidal
- Ensure new methods are optional dependencies
- Add appropriate tests comparing accuracy

## Motor Validation

When adding validation rules:

- Make validation configurable (warnings vs errors)
- Base rules on real-world motor characteristics
- Provide clear, actionable error messages

## Documentation

- Use clear, concise docstrings
- Include examples in docstrings where helpful
- Update README.md for significant changes
- Use type hints consistently

## Questions?

Feel free to open an issue for:

- Questions about contributing
- Suggestions for improvements
- Bug reports
- Feature requests

## License

By contributing, you agree that your contributions will be licensed under the same license as the project (MIT License).
