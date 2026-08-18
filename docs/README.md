# Chrome File Directory — Documentation

A static reproduction of the Chromium browser's file directory listing UI. Two HTML files, a
folder of PNG icons, and no server-side component.

```
Chrome-File-Directory/
├── docs/
│   ├── README.md          this page
│   ├── quickstart.md      see it, then make it yours
│   ├── installation.md    there is nothing to install
│   ├── usage.md           editing the listing
│   ├── configuration.md   external stylesheet and icon changes
│   ├── architecture.md    the two HTML files, and which to use
│   ├── deployment.md      web server, Docker, GitHub Pages
│   ├── faq.md             which file, automatic listings, licensing
│   ├── troubleshooting.md broken icons, the style.css path bug
│   ├── roadmap.md         known gaps and non-goals
│   └── legal/             privacy policy and terms
├── index.html             the simplified, editable page
├── index_chromium.html    the original Chromium page, kept for reference
├── style.css              optional external stylesheet
└── icons/                 file.png, folder.png, up.png
```

## Pages

- [Quickstart](./quickstart.md) — open it, edit it, publish it
- [Installation](./installation.md) — clone or download; there is no install step
- [Usage](./usage.md) — setting the title and adding rows
- [Configuration](./configuration.md) — the external stylesheet and changing icons
- [Architecture](./architecture.md) — why there are two HTML files
- [Deployment](./deployment.md) — your server, Docker, or GitHub Pages
- [FAQ](./faq.md) — which file to use, does it list files automatically
- [Troubleshooting](./troubleshooting.md) — missing icons, the `style.css` path problem
- [Roadmap](./roadmap.md) — known gaps and deliberate non-goals

## Two things to know first

**Edit `index.html`, not `index_chromium.html`.** The first is a simplified 135-line page meant
to be customised. The second is the original Chromium page — 512 lines including JavaScript —
kept unmodified as a reference and for attribution.

**The page does not read a directory.** It is a hand-written listing that looks like one.
Nothing scans a folder and nothing keeps it in sync.

## Related

The same idea in two other styles:
[Apache](https://github.com/willtheorangeguy/Apache-File-Directory) and
[Nginx](https://github.com/willtheorangeguy/Nginx-File-Directory).
