# Chrome File Directory — Roadmap

Known gaps, observed from the repository. Limitations, not a schedule.

## Confirmed bug

**`style.css` points at a directory that does not exist.** It references `imgs/file.png`,
`imgs/folder.png`, and `imgs/up.png`; the icons ship in `icons/`, and there is no `imgs/`
directory anywhere in the repository.

The documentation tells you to copy `style.css` and link it from `index.html`, so anyone
following those instructions ends up with every icon broken. The inline styling in
`index.html` uses the correct path, which is why this stays hidden until someone opts in.

Either the stylesheet paths or the directory name should change — a one-line fix in whichever
direction you prefer.

## Not gaps

Two things look like omissions and are not:

**The simplified page does not generate listings.** Being hand-written is the point of
`index.html`. `index_chromium.html` is the original page that does build its listing
dynamically, kept unmodified for reference.

**There are two HTML files.** That is deliberate: one to edit, one to attribute.

## Real gaps

**Nothing validates the listing.** Links, dates, and sizes are hand-typed, with no check that a
row points at a file that exists.

**The example rows are a trap.** The shipped `index.html` includes samples, and forgetting to
delete them advertises files that are not there. Shipping them commented out would make the
mistake impossible.

**`icons/` is easy to leave behind**, which breaks every image.

**The two styling paths have drifted.** Inline styles and `style.css` are meant to be
equivalent alternatives and are not currently in sync — the icon-path bug above is the visible
symptom.

## Repository hygiene

**The Docker workflow filename is misspelled**: `docker-pubish.yml` rather than
`docker-publish.yml`. It works, since the README badge points at the same name, but it differs
from [Apache](https://github.com/willtheorangeguy/Apache-File-Directory) and
[Nginx](https://github.com/willtheorangeguy/Nginx-File-Directory). Renaming it means updating
the badge in the same commit.

**Per-repo issue templates override the org defaults.** `.github/ISSUE_TEMPLATE/` holds
Markdown templates predating the org-level YAML forms, and GitHub prefers local ones. Removing
them would inherit the shared set.

## Licensing note

The project is BSD 2-Clause while Chromium is BSD 3-Clause. The upstream notice is preserved in
`LICENSE_chromium.md` alongside the unmodified `index_chromium.html`, which is the right
arrangement — but anyone redistributing material derived from the Chromium page is governed by
the upstream terms rather than this project's.

## Non-goals

- **Being a real directory index.** The browser already does that.
- **Modifying `index_chromium.html`.** It is a reference copy; its value is being unchanged.
- **A build step.** Deployment is copying two paths.
