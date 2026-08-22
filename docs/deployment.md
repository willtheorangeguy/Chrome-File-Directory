# Chrome File Directory — Deployment

## On your own web server

1. Download the latest `.zip` from
   [GitHub Releases](https://github.com/willtheorangeguy/Chrome-File-Directory/releases/latest),
   or clone the repository.
2. Copy `index.html` **and the `icons/` folder** to the directory you want listed.
3. Edit `index.html` to describe the files that are actually there — see [Usage](./usage.md).
4. Upload.

Forgetting `icons/` is the usual mistake: every row then shows a broken image, because icons
are relative paths.

`index_chromium.html` and `style.css` do not need to travel with it.

## With Docker

```bash
docker pull ghcr.io/willtheorangeguy/chrome-file-directory:main
docker run -d -p 8000:80 ghcr.io/willtheorangeguy/chrome-file-directory:main
```

Then <http://localhost:8000/>.

**The image name is lowercase.** GHCR requires it, so `Chrome-File-Directory` will not pull
even though that is the repository name.

## Building it yourself

```bash
docker build -t cfd .
docker run -d -p 8000:80 cfd
```

Useful for previewing your edited copy rather than the published one.

## GitHub Pages

`docs.yml` deploys on every push to `main`, which keeps
<https://willtheorangeguy.github.io/Chrome-File-Directory/> current.

Forking and enabling Pages gives you the same for your own copy — a hosted listing with no
server to run.

## Automation

| Workflow            | Trigger        | Does                        |
| ------------------- | -------------- | --------------------------- |
| `docs.yml`         | push to `main` | Deploys to GitHub Pages     |
| `docker-pubish.yml` | push to `main` | Builds and pushes to GHCR   |
| `gitleaks.yml`      | pushes and PRs | Scans for committed secrets |

The Docker workflow filename is misspelled. It works — the README badge points at the same
name — but it differs from the sibling repositories.

## Nothing to configure

No environment variables, no database, no build step. Deployment is copying files.
