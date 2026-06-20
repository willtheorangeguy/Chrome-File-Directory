# CLAUDE.md

## Project Overview

Chrome File Directory is a static HTML page that replicates the Chromium browser's file/directory listing UI. It provides a customizable template for displaying files and folders in a familiar Chrome-style layout. Originally derived from Chromium source code (BSD-licensed), with additional modifications by @willtheorangeguy.

## Repository Structure

```
├── index.html            # Main file directory page (simplified, customizable version)
├── index_chromium.html   # Original Chromium file directory page (reference)
├── style.css             # External stylesheet (references imgs/ for icons)
├── icons/                # Icon assets (file.png, folder.png, up.png)
├── docs/                 # Documentation site (usage, customization, legal)
├── Dockerfile            # Nginx-based container for serving the page
├── package.json          # npm metadata (no dependencies or real scripts)
├── .github/
│   ├── workflows/        # CI: GitHub Pages deploy, Docker build/push, GitLeaks
│   ├── ISSUE_TEMPLATE/   # Bug report, feature request, question templates
│   ├── agents/           # GitHub Copilot agent configs (docs, lint, test)
│   └── dependabot.yml    # Automated dependency updates
```

## Key Files

- **`index.html`** — The primary deliverable. A self-contained HTML page with inline CSS. Edit this to customize the directory listing. Icons reference `icons/` directory.
- **`style.css`** — External stylesheet variant. Note: icon paths use `imgs/` (differs from `index.html` which uses `icons/`).
- **`index_chromium.html`** — The original unmodified Chromium source. Keep as reference; do not modify.

## Development

**No build step or dependencies.** This is a pure static HTML/CSS project. Open `index.html` in a browser to preview.

**Running locally with Docker:**
```bash
docker build -t chrome-file-directory .
docker run -p 8080:80 chrome-file-directory
```

**No test suite exists.** The `npm test` script is a placeholder that exits with an error.

## CI/CD Workflows

- **Pages** (`pages.yml`): Deploys to GitHub Pages on push to `main`.
- **Docker** (`docker-pubish.yml`): Builds and pushes to `ghcr.io` on push to `main`, tags, PRs, and daily schedule.
- **GitLeaks** (`gitleaks.yml`): Scans for secrets on push, PR, and manual trigger.

## Code Conventions

- Dual copyright headers: Chromium BSD + @willtheorangeguy. Preserve both in modified files.
- HTML uses 2-space indentation.
- CSS uses 2-space indentation.
- Prettier is configured as a transformer via DeepSource (`.deepsource.toml`).
- Commit messages follow conventional commits style: `feat(scope):`, `fix(scope):`, `build(deps):`.

## Licensing

- BSD-2-Clause (primary, `LICENSE.md`)
- Chromium BSD license (`LICENSE_chromium.md`) applies to original Chromium-derived code

## Contributing

Follow GitHub Flow: branch, commit, open PR. See `CONTRIBUTING.md` for full guidelines. Use provided issue templates for bugs, features, and questions.
