# Chrome File Directory — Architecture

## What is in the repository

```
index.html            the simplified, editable page (135 lines)
index_chromium.html   the original Chromium page (512 lines, includes JavaScript)
style.css             optional external stylesheet
icons/                file.png, folder.png, up.png
Dockerfile            Nginx, serving the static files
```

## Two HTML files, one to edit

This is the thing to understand before touching anything.

**`index.html`** is a stripped-down version: styling inline, no scripts, a table you can read
and edit by hand. This is the file the documentation refers to and the one you customise.

**`index_chromium.html`** is the original page from Chromium, kept unmodified. It is four
times the size and contains six script blocks, because the real browser page builds its
listing dynamically. It exists for reference and for honest attribution — not for editing.

The distinction also explains a feature claim that would otherwise be confusing: the
*Chromium* page generates listings; the simplified one does not.

## Static means hand-maintained

`index.html` does not read a directory. Every row exists because someone typed it, and nothing
validates that a link resolves or a size is accurate.

| Property | Because |
|---|---|
| Works from `file://` | Nothing is fetched |
| Deploys by copying files | There is nothing to build |
| Goes stale silently | Nothing re-reads the directory |

A browser generates this listing when it opens a local folder. This is a picture of one.

## Styling: inline by default, external optional

`index.html` carries its styling inline, which is what makes it self-contained and portable.

`style.css` is offered as an alternative for people who prefer external CSS — it is not linked
by default, and using it is an opt-in documented in [Configuration](./configuration.md).

The two are not currently in sync: the inline styles reference `icons/`, while `style.css`
references `imgs/`, a directory that does not exist in this repository. Anyone following the
documented instructions to adopt the stylesheet gets broken icons — see
[Roadmap](./roadmap.md).

## Icons

Three PNGs — `file.png`, `folder.png`, `up.png` — referenced by relative path. That keeps the
page portable and means copying only the HTML breaks every image.

## Docker

`Dockerfile` is Nginx serving the static files, for convenience rather than necessity.

## Automation

| Workflow | Purpose |
|---|---|
| `pages.yml` | Deploys to GitHub Pages on push to `main` |
| `docker-pubish.yml` | Publishes the image to GHCR |
| `gitleaks.yml` | Scans for committed secrets |

The Docker workflow filename is misspelled — `docker-pubish.yml` rather than
`docker-publish.yml`. It works, because the badge in the README points at the same misspelled
name, but it differs from the sibling repositories.

## No tests

None, and for a static page that is defensible — verification is opening it and looking.
