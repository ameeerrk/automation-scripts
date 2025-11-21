# Contributing to Automation Scripts

Thank you for your interest in contributing to this automation scripts collection! This document provides guidelines for contributing to the project.

## 📋 Table of Contents

- [Code of Conduct](#code-of-conduct)
- [How Can I Contribute?](#how-can-i-contribute)
- [Development Guidelines](#development-guidelines)
- [Submitting Changes](#submitting-changes)

## Code of Conduct

This project follows a simple code of conduct:
- Be respectful and inclusive
- Provide constructive feedback
- Focus on what is best for the community

## How Can I Contribute?

### Reporting Bugs

If you find a bug, please create an issue with:
- A clear, descriptive title
- Steps to reproduce the issue
- Expected vs actual behavior
- Your environment (OS, language version, etc.)

### Suggesting Enhancements

Enhancement suggestions are welcome! Please create an issue with:
- A clear description of the enhancement
- Why this enhancement would be useful
- Examples of how it would work

### Adding New Scripts

1. Fork the repository
2. Create a new branch (`git checkout -b feature/your-script-name`)
3. Add your script in the appropriate language directory
4. Include a README.md with your script following the template below
5. Ensure your script follows the development guidelines
6. Commit your changes with clear commit messages
7. Push to your branch
8. Open a Pull Request

## Development Guidelines

### Script Requirements

All scripts should:
- **Be well-documented**: Include clear comments explaining what the script does
- **Include a README**: Each script should have its own README with:
  - Description
  - Prerequisites
  - Installation steps
  - Usage examples
  - Known limitations
- **Handle errors**: Include proper error handling and validation
- **Follow best practices**: Use language-specific best practices
- **Be standalone**: Scripts should be self-contained when possible

### Code Style

#### Python
- Follow PEP 8 style guidelines
- Use meaningful variable names
- Include docstrings for functions and classes
- Use type hints where appropriate

#### Bash
- Use `#!/bin/bash` shebang
- Quote variables
- Check command exit codes
- Use functions for reusable code

#### JavaScript
- Follow modern ES6+ standards
- Use `const`/`let` instead of `var`
- Include JSDoc comments
- Handle promises/async operations properly

#### PowerShell
- Follow PowerShell best practices
- Use approved verbs for functions
- Include comment-based help
- Use proper error handling with try/catch

### Script README Template

```markdown
# Script Name

Brief description of what the script does.

## Description

Detailed description of the script's functionality.

## Prerequisites

- Requirement 1
- Requirement 2

## Installation

```bash
# Installation steps
```

## Usage

```bash
# Usage example
```

### Options

- `--option1`: Description
- `--option2`: Description

## Examples

```bash
# Example 1
command example1

# Example 2
command example2
```

## Known Limitations

- Limitation 1
- Limitation 2

## Author

Your Name (@your-github-username)
```

## Submitting Changes

1. Ensure your code follows the development guidelines
2. Test your script thoroughly
3. Update documentation as needed
4. Write clear, concise commit messages
5. Create a Pull Request with:
   - Clear title describing the change
   - Description of what was added/changed
   - Reference to any related issues

## Questions?

Feel free to open an issue with the "question" label if you need clarification on anything.

Thank you for contributing! 🎉
