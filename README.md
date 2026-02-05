# Platform-Docs

The official public documentation site for the Vindicta Platform ecosystem.

## Overview

This repository hosts the MkDocs-based documentation for the entire Vindicta Platform. It aggregates platform-wide guides, architecture overviews, and cross-cutting concerns that span multiple repositories.

## Features

- **Platform Architecture**: High-level system design and integration patterns
- **Getting Started**: Unified onboarding for new developers and users
- **API Reference**: Cross-repository API documentation
- **Governance**: Platform-wide policies and constitution

## Local Development

```bash
# Install dependencies
pip install mkdocs mkdocs-material

# Serve locally
mkdocs serve

# Build static site
mkdocs build
```

## Deployment

This site is automatically deployed to GitHub Pages on push to `main`.

## Repository Structure

```
Platform-Docs/
├── docs/           # Documentation source files
│   ├── adr/        # Architecture Decision Records
│   └── index.md    # Homepage
├── mkdocs.yml      # MkDocs configuration
└── README.md       # This file
```

## Related Repositories

| Repository | Description |
|------------|-------------|
| [platform-core](https://github.com/vindicta-platform/platform-core) | Core platform implementation |
| [WARScribe-CLI](https://github.com/vindicta-platform/WARScribe-CLI) | Command-line interface |
| [Logi-Slate-UI](https://github.com/vindicta-platform/Logi-Slate-UI) | Tactical management UI |

## License

MIT License - See [LICENSE](./LICENSE) for details.
