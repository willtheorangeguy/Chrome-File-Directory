# Chrome File Directory — Troubleshooting

## Icons are broken after switching to style.css

A confirmed bug rather than anything you did.

`style.css` references its icons as `imgs/file.png`, `imgs/folder.png`, and `imgs/up.png` —
but this repository ships them in **`icons/`**. There is no `imgs/` directory, so every icon
fails to load.

Two fixes:

- Edit `style.css` to point at `icons/`, or
- Create an `imgs/` directory containing copies of the three PNGs.

The inline styling in `index.html` uses the correct path, so this only affects people who
followed the documented steps to adopt the external stylesheet. Recorded in
[Roadmap](./roadmap.md).

## Icons are broken and I am not using style.css

`icons/` was not copied alongside `index.html`. Both need to travel together.

## I edited the page and nothing changed

Check which file you edited. `index.html` is the simplified, editable page;
`index_chromium.html` is the original Chromium reference copy. See
[Architecture](./architecture.md).

## A link goes nowhere

Every link is hand-written and nothing validates it. Check the `href` matches the real
filename — including case, on a case-sensitive server — and that the path is relative to where
`index.html` actually sits.

## The listing shows files that are not there

Leftover example rows. Delete every row you did not customise — see [Usage](./usage.md).

## `docker pull` fails with a name error

Use lowercase:

```bash
docker pull ghcr.io/willtheorangeguy/chrome-file-directory:main
```

GHCR requires lowercase image names.

## The container starts but the page is blank

Check the port mapping. The container serves on 80 internally; the documented command maps it
to 8000, so use <http://localhost:8000/>.

## GitHub Pages is not updating

`docs.yml` deploys on push to `main`. Check the Actions tab — the badge in the README
reflects the last run.

Note the Docker workflow is `docker-pubish.yml`, spelled that way on purpose in the badge; if
you are looking for `docker-publish.yml` you will not find it.

## Dates and sizes are wrong

They are plain text and nothing computes them.
