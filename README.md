# Ghost Team CI

Reusable GitHub Actions workflows for all Ghost Team repos.

## Usage

### Next.js / TypeScript apps

```yaml
# .github/workflows/ci.yml
name: CI
on:
  push:
    branches: [main]
  pull_request:
    branches: [main]

jobs:
  ci:
    uses: vincentmcleese/ghost-team-ci/.github/workflows/nextjs.yml@main
```

### Python scrapers

```yaml
# .github/workflows/ci.yml
name: CI
on:
  push:
    branches: [main]
  pull_request:
    branches: [main]

jobs:
  ci:
    uses: vincentmcleese/ghost-team-ci/.github/workflows/python.yml@main
```

### Options

#### Next.js
| Input | Default | Description |
|-------|---------|-------------|
| `node-version` | `22` | Node.js version |
| `working-directory` | `.` | Working dir (for monorepos) |
| `skip-test` | `false` | Skip test step |

#### Python
| Input | Default | Description |
|-------|---------|-------------|
| `python-version` | `3.12` | Python version |
| `working-directory` | `.` | Working dir |
| `install-command` | `""` | Custom install (default: `pip install -r requirements.txt`) |

## What's checked

**Next.js:** install → lint → typecheck → test → build  
**Python:** install → ruff lint → pyright typecheck → pytest

## Repos using this

- [appsdiscoverability](https://github.com/vincentmcleese/appsdiscoverability)
- [planningapp](https://github.com/vincentmcleese/planningapp)
- [appstore-data](https://github.com/vincentmcleese/appstore-data)
- [chatgpt-scraper](https://github.com/vincentmcleese/chatgpt-scraper)
- [apps-docs-scanner](https://github.com/vincentmcleese/apps-docs-scanner)
