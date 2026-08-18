# Chrome File Directory — Installation

There is no installation. It is static HTML with a folder of PNG icons — no build step, no
dependencies, no runtime.

## Get the files

```bash
git clone https://github.com/willtheorangeguy/Chrome-File-Directory.git
cd Chrome-File-Directory
```

Or download the latest `.zip` from
[GitHub Releases](https://github.com/willtheorangeguy/Chrome-File-Directory/releases/latest).

## Run it

Open `index.html` in any browser. It works from the filesystem — nothing on the page fetches
anything.

## What you need to copy

| Path | Required |
|---|---|
| `index.html` | Yes — this is the page you edit |
| `icons/` | Yes — icons are referenced by relative path |
| `index_chromium.html` | No — reference copy only |
| `style.css` | Only if you want an external stylesheet; see below |

Copying `index.html` alone leaves broken images in every row, which is the usual first-time
problem.

## About `style.css`

`index.html` carries its own styling inline and does **not** link `style.css`. The stylesheet
is an optional alternative for people who prefer external CSS.

If you use it, note that its icon paths currently point at `imgs/` while the icons actually
live in `icons/` — see [Troubleshooting](./troubleshooting.md).

## Container image

```bash
docker pull ghcr.io/willtheorangeguy/chrome-file-directory:main
docker run -d -p 8000:80 ghcr.io/willtheorangeguy/chrome-file-directory:main
```

Lowercase image name; GHCR requires it.

## Next

[Quickstart](./quickstart.md), or [Usage](./usage.md) to start editing.
