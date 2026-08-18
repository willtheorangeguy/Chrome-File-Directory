# Chrome File Directory — Quickstart

## 1. See it

Live at <https://willtheorangeguy.github.io/Chrome-File-Directory/>, or locally:

```bash
git clone https://github.com/willtheorangeguy/Chrome-File-Directory.git
cd Chrome-File-Directory
```

Open `index.html` in a browser. No server needed.

## 2. Use the right file

| File                  | Use it?                                                                      |
| --------------------- | ---------------------------------------------------------------------------- |
| `index.html`          | **Yes.** 135 lines, simplified, meant to be edited                           |
| `index_chromium.html` | No. The original Chromium page, 512 lines with JavaScript, kept as reference |

Editing the wrong one is the easiest mistake here — see [Architecture](./architecture.md).

## 3. Make it yours

Open `index.html` in a text editor, set the title, and add a row per file or folder following
the examples already there.

Then **delete the example rows you did not use** — they point at files that do not exist, and
nothing will warn you.

Full walkthrough in [Usage](./usage.md).

## 4. Publish

Copy `index.html` **and the `icons/` folder** to your web server. Icons are referenced by
relative path, so leaving the folder behind gives broken images.

Other options in [Deployment](./deployment.md).

## Try it in Docker

```bash
docker run -d -p 8000:80 ghcr.io/willtheorangeguy/chrome-file-directory:main
```

Then <http://localhost:8000/>. The image name is **lowercase** — GHCR requires it.

## Know this before you use it

It does not list a real directory. It shows exactly what you typed and nothing more. See
[FAQ](./faq.md).
