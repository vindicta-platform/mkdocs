# Quick Start

Get Vindicta running in 5 minutes.

---

## Prerequisites

- Python 3.10+
- [uv](https://github.com/astral-sh/uv) (recommended)
- Docker & Docker Compose (for full platform)
- A terminal

## Option 1: Unified CLI

The `Vindicta-CLI` provides a unified entry point for all platform tools.

```bash
# Clone the CLI repository
git clone https://github.com/vindicta-platform/Vindicta-CLI.git
cd Vindicta-CLI

# Install with uv
uv sync
source .venv/bin/activate

# Verify installation
vindicta --version
```

## Option 2: Full Platform (Docker)

Run the entire suite (Portal, Engine, Oracle) locally using Docker.

```bash
# Clone the Orchestrator / Platform Root
git clone https://github.com/vindicta-platform/vindicta-platform.git
cd vindicta-platform

# Start all services
docker-compose up -d

# Access the Portal
# Open http://localhost:3000
```

## Option 3: Interface Only (Portal)

If you only want to work on the frontend:

```bash
git clone https://github.com/vindicta-platform/Vindicta-Portal.git
cd Vindicta-Portal
npm install
npm run dev

# Open http://localhost:3000
```

---

## Next Steps

- [Installation Guide](installation.md) — Detailed setup instructions for each meso-repository.
- [WARScribe System](../features/army-management.md) — Learn the notation format.
- [Architecture](../architecture/overview.md) — Understand how the modules connect.
