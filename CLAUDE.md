# CLAUDE.md - AI Assistant Guide for Sim2AutoTest

## Project Overview

**Repository:** Sim2AutoTest
**Owner:** JerryLien
**Purpose:** Simulation-to-Automated-Testing framework/tool

This project aims to bridge simulation environments with automated testing workflows, enabling automated test generation, execution, and validation from simulation data.

---

## Repository Structure

```
Sim2AutoTest/
├── src/                    # Source code
│   ├── core/              # Core simulation processing logic
│   ├── converters/        # Simulation format converters
│   ├── generators/        # Test case generators
│   └── utils/             # Utility functions
├── tests/                 # Test suite
│   ├── unit/             # Unit tests
│   ├── integration/      # Integration tests
│   └── fixtures/         # Test fixtures and sample data
├── docs/                  # Documentation
│   ├── architecture.md   # System architecture
│   ├── api.md           # API documentation
│   └── examples/        # Usage examples
├── config/               # Configuration files
├── scripts/             # Build and deployment scripts
├── .github/             # GitHub workflows and templates
├── README.md            # Project README
├── CONTRIBUTING.md      # Contribution guidelines
└── CLAUDE.md           # This file - AI assistant guide
```

**Note:** As this is a new repository, this structure is recommended but may evolve based on project needs.

---

## Codebase Conventions

### Code Style

**To be determined based on chosen language stack. Common practices:**

- Follow language-specific style guides (PEP 8 for Python, Google Style for Java, etc.)
- Use meaningful variable and function names
- Write self-documenting code with clear comments for complex logic
- Keep functions focused and single-purpose
- Maximum line length: 100-120 characters

### Naming Conventions

- **Files:** `snake_case` for Python, `camelCase` for JavaScript/TypeScript, `PascalCase` for classes
- **Functions/Methods:** `snake_case` (Python) or `camelCase` (JS/TS/Java)
- **Classes:** `PascalCase`
- **Constants:** `UPPER_SNAKE_CASE`
- **Private members:** Prefix with `_` (Python) or use language-specific conventions

### Testing Standards

- Aim for >80% code coverage
- Write tests before fixing bugs (TDD approach preferred)
- Name test functions descriptively: `test_<feature>_<scenario>_<expected_result>`
- Use fixtures and mocks appropriately
- Keep tests isolated and independent

---

## Development Workflow

### Branch Strategy

- **Main Branch:** `main` or `master` - Production-ready code
- **Development Branch:** `develop` - Integration branch for features
- **Feature Branches:** `feature/<feature-name>` - New features
- **Bug Fixes:** `bugfix/<issue-number>-<description>` or `fix/<description>`
- **Hotfixes:** `hotfix/<issue>` - Critical production fixes
- **AI Development:** `claude/<session-id>` - AI assistant work branches

### Commit Message Format

Follow Conventional Commits specification:

```
<type>(<scope>): <subject>

<body>

<footer>
```

**Types:**
- `feat`: New feature
- `fix`: Bug fix
- `docs`: Documentation changes
- `style`: Code style changes (formatting, no logic change)
- `refactor`: Code refactoring
- `test`: Adding or updating tests
- `chore`: Maintenance tasks, dependency updates
- `perf`: Performance improvements

**Example:**
```
feat(converter): add support for CSV simulation data

Implement CSV parser that handles various delimiter formats
and converts simulation output to standardized test format.

Closes #123
```

### Pull Request Process

1. Create feature branch from `develop`
2. Implement changes with tests
3. Ensure all tests pass
4. Update documentation if needed
5. Create PR with clear description
6. Address review feedback
7. Squash commits if requested
8. Merge after approval

---

## Key Technical Decisions

### Technology Stack

**To be determined. Recommendations based on project scope:**

- **Backend:** Python (for data processing) or Java/TypeScript (for enterprise integration)
- **Testing Framework:** pytest (Python), JUnit (Java), Jest (TypeScript)
- **Build Tool:** Make, Maven, Gradle, or npm scripts
- **CI/CD:** GitHub Actions
- **Documentation:** Markdown, Sphinx, or JSDoc

### Architecture Patterns

- **Modular Design:** Separate concerns (simulation parsing, test generation, execution)
- **Plugin Architecture:** Support multiple simulation formats via plugins
- **Configuration-Driven:** Use config files for flexibility
- **Dependency Injection:** For testability and maintainability

---

## AI Assistant Guidelines

### When Working on This Codebase

#### 1. Understanding Context

- **Always read existing code** before making changes
- **Check for related tests** to understand expected behavior
- **Review recent commits** to understand ongoing work
- **Look for TODO comments** that indicate planned work
- **Consult documentation** in `docs/` directory

#### 2. Code Changes

- **Prefer editing existing files** over creating new ones
- **Maintain consistency** with existing code style
- **Add tests** for all new functionality
- **Update documentation** when changing APIs or behavior
- **Avoid breaking changes** without discussion
- **Use type hints/annotations** where supported

#### 3. Testing Requirements

- **Run existing tests** before committing: `pytest` / `npm test` / `mvn test`
- **Write unit tests** for new functions
- **Add integration tests** for new features
- **Verify edge cases** are covered
- **Check test coverage** and aim to maintain/improve it

#### 4. Security Considerations

- **Never commit secrets** (API keys, passwords, tokens)
- **Validate all inputs** to prevent injection attacks
- **Sanitize file paths** to prevent path traversal
- **Use parameterized queries** for any database operations
- **Follow principle of least privilege** for permissions
- **Keep dependencies updated** for security patches

#### 5. Performance Best Practices

- **Profile before optimizing** - measure, don't guess
- **Use appropriate data structures** for the task
- **Avoid premature optimization**
- **Cache expensive operations** when appropriate
- **Stream large files** instead of loading into memory
- **Consider async/parallel processing** for I/O operations

#### 6. Documentation Standards

- **Update README.md** when adding new features
- **Document public APIs** with docstrings/JSDoc
- **Add inline comments** for complex logic
- **Update CHANGELOG.md** for user-facing changes
- **Create examples** for new functionality

#### 7. Git Workflow for AI Assistants

- **Work on `claude/<session-id>` branches**
- **Commit frequently** with descriptive messages
- **Push to origin** with: `git push -u origin <branch-name>`
- **Create clear PR descriptions** with context
- **Reference issue numbers** in commits and PRs
- **Never force push** unless explicitly requested
- **Retry network operations** up to 4 times with exponential backoff

#### 8. Communication

- **Ask questions** when requirements are unclear
- **Suggest alternatives** when appropriate
- **Explain technical decisions** in PR descriptions
- **Highlight breaking changes** prominently
- **Document assumptions** made during implementation

---

## Common Tasks Reference

### Setting Up Development Environment

```bash
# Clone repository
git clone <repository-url>
cd Sim2AutoTest

# Install dependencies (language-specific)
# Python: pip install -r requirements.txt
# Node: npm install
# Java: mvn install

# Run tests
# Python: pytest
# Node: npm test
# Java: mvn test

# Build project (if applicable)
# make build
# npm run build
# mvn package
```

### Running Tests

```bash
# Run all tests
<test-command>

# Run specific test file
<test-command> path/to/test_file

# Run with coverage
<test-command> --coverage

# Run in watch mode (if supported)
<test-command> --watch
```

### Adding a New Feature

1. Create feature branch: `git checkout -b feature/my-feature`
2. Implement feature with tests
3. Run test suite to ensure nothing breaks
4. Update documentation
5. Commit changes: `git commit -m "feat: add my feature"`
6. Push branch: `git push -u origin feature/my-feature`
7. Create pull request

### Debugging

- **Use logging** instead of print statements
- **Set breakpoints** in IDE or use debugger
- **Check logs** in appropriate location
- **Reproduce with minimal example** when filing bugs
- **Include stack traces** in bug reports

---

## Project-Specific Notes

### Simulation Format Support

**To be documented as formats are added:**

- CSV
- JSON
- XML
- Custom binary formats
- Vendor-specific formats

### Test Output Formats

**To be documented as generators are added:**

- JUnit XML
- pytest format
- Custom formats
- CI/CD integration formats

### Integration Points

**External systems this project integrates with:**

- Simulation software (to be specified)
- Testing frameworks
- CI/CD pipelines
- Reporting tools

---

## Troubleshooting

### Common Issues

**To be populated as issues arise:**

1. **Issue:** Description
   - **Solution:** Step-by-step fix
   - **Prevention:** How to avoid in future

### Getting Help

- Check documentation in `docs/`
- Review existing issues in GitHub
- Search commit history for similar changes
- Consult project maintainers

---

## Resources

### Internal Documentation

- [Architecture Documentation](docs/architecture.md) - System design and structure
- [API Documentation](docs/api.md) - API reference
- [Contributing Guide](CONTRIBUTING.md) - How to contribute
- [Examples](docs/examples/) - Usage examples

### External Resources

- Relevant simulation format specifications
- Testing framework documentation
- Language-specific best practices
- Related projects and tools

---

## Changelog

### Version History

- **Initial Setup** (2025-11-14): Repository created, CLAUDE.md established

---

## Maintenance

### Regular Tasks

- Update dependencies monthly
- Review and close stale issues
- Update documentation with new features
- Maintain test coverage >80%
- Review security advisories

### Documentation Updates

**This CLAUDE.md file should be updated when:**

- Project structure changes significantly
- New conventions are adopted
- Technology stack decisions are made
- Major features are added
- Development workflow changes

---

## Contact & Support

- **Repository Owner:** JerryLien
- **Issues:** Use GitHub Issues for bug reports and feature requests
- **Discussions:** Use GitHub Discussions for questions and ideas

---

*Last Updated: 2025-11-14*
*Document Version: 1.0*
