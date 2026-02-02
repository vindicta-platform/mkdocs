# Code Standards

Guidelines for contributing to Vindicta.

---

## Python

- **Version**: 3.10+
- **Formatter**: Ruff
- **Type Hints**: Required
- **Async**: Preferred for I/O

## Testing

- **Unit Tests**: pytest
- **BDD**: behave
- **Coverage**: 80% minimum

## Commit Messages

Follow conventional commits:

```
feat: add new dice roller
fix: correct entropy proof generation
docs: update installation guide
```

## Pull Requests

1. Create feature branch
2. Write tests first (TDD)
3. Ensure CI passes
4. Request review

---

## Constitution

All code must follow the [Platform Constitution](https://github.com/vindicta-platform/platform-core/blob/main/.specify/memory/constitution.md).
