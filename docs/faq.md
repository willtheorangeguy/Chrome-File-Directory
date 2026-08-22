# Chrome File Directory — FAQ

## Which file do I edit?

`index.html`. It is the simplified 135-line version meant to be customised.

`index_chromium.html` is the original Chromium page — 512 lines including JavaScript — kept
unmodified for reference and attribution. Editing it is almost never what you want.

## Does it list my files automatically?

The simplified `index.html` does not. It is a hand-written table that looks like a listing;
nothing scans a folder and nothing keeps it in sync.

The original Chromium page builds its listing dynamically, which is where the "automatically
generated file listing" claim comes from. That behaviour belongs to the browser page, not to
the editable copy.

## Then what is it for?

Anywhere you want the appearance of a Chromium directory index without a browser producing
one — a placeholder, a curated list, a mock-up, or serving a fixed set of files from static
hosting.

## Why are the icons broken?

Either `icons/` was not copied alongside `index.html`, or you adopted `style.css`, whose icon
paths point at `imgs/` — a directory that does not exist here. See
[Troubleshooting](./troubleshooting.md).

## Do I need `style.css`?

No. `index.html` carries its styling inline and does not link it. The stylesheet is an
optional alternative for people who prefer external CSS.

## Why does `docker pull` fail?

The image name is lowercase — `ghcr.io/willtheorangeguy/chrome-file-directory`. GHCR requires
lowercase, so the capitalised repository name will not work.

## The listing shows files that do not exist

Leftover example rows from the shipped file. Deleting the ones you did not customise is a
manual step nothing can check. See [Usage](./usage.md).

## Why is the project BSD 2-Clause when Chromium is BSD 3-Clause?

Chromium is BSD 3-Clause, and its notice is preserved in `LICENSE_chromium.md` alongside the
unmodified `index_chromium.html`. The project's own licence is BSD 2-Clause.

If you are redistributing anything derived from the Chromium page, the upstream terms are the
ones that govern it.

## Is there a version for other servers?

Yes: [Apache](https://github.com/willtheorangeguy/Apache-File-Directory) and
[Nginx](https://github.com/willtheorangeguy/Nginx-File-Directory).

## Are the dates and sizes accurate?

They are plain text. Nothing computes them, so they are as accurate as you make them.
