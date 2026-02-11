# Installation

Detailed installation instructions for each platform component.

---

## Core Requirements

All Vindicta components require:

- **Python 3.10+** (for backend components)
- **Node.js 18+** (for UI components)
- **uv** (recommended package manager)

### Installing uv

```bash
# macOS/Linux
curl -LsSf https://astral.sh/uv/install.sh | sh

# Windows
powershell -c "irm https://astral.sh/uv/install.ps1 | iex"
```

---

## Component Installation

### Platform Core

The central integration layer:

```bash
git clone https://github.com/vindicta-platform/platform-core.git
cd platform-core
uv venv
uv pip install -e ".[dev]"
```

### Vindicta-Portal

The unified web interface for the platform.

```bash
git clone https://github.com/vindicta-platform/Vindicta-Portal.git
cd Vindicta-Portal
```

### Individual Modules

Each module can be installed independently:

```bash
# Core Platform
uv pip install git+https://github.com/vindicta-platform/vindicta-foundation.git
uv pip install git+https://github.com/vindicta-platform/vindicta-engine.git

# Logic & Data
uv pip install git+https://github.com/vindicta-platform/warscribe-system.git
uv pip install git+https://github.com/vindicta-platform/vindicta-economy.git
uv pip install git+https://github.com/vindicta-platform/vindicta-oracle.git
```

npm install
npm run dev
```

---

## Verification

Verify your installation:

```bash
# Check CLI
vindicta --version

# Check API
curl http://localhost:8000/health

# Run tests
pytest tests/ -v
```

---

## Troubleshooting

### uv lock file issues

```bash
uv cache clean
rm uv.lock
uv sync
```

### Port already in use

```bash
# Find process on port 8000
lsof -i :8000
# or on Windows
netstat -ano | findstr :8000
```
