# Development Setup

Set up your development environment.

---

## Prerequisites

- Python 3.10+
- Node.js 18+ (for UI)
- uv package manager
- Git

## Clone the Platform

```bash
git clone https://github.com/vindicta-platform/platform-core.git
cd platform-core
```

## Install Dependencies

```bash
uv venv
uv pip install -e ".[dev]"
```

## Run Tests

```bash
pytest tests/ -v
behave tests/features/
```

## Start Development Server

```bash
uvicorn vindicta.api:app --reload
```

## Code Quality

```bash
ruff check .
ruff format .
```

---

## Module Development

To work on individual modules:

```bash
git clone https://github.com/vindicta-platform/<module-name>.git
cd <module-name>
uv venv
uv pip install -e ".[dev]"
```
