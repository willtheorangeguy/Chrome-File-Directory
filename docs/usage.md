# Chrome File Directory — Usage

The page is a static HTML table styled to look like Chromium's directory listing. Using it
means editing that table to describe your files.

**Edit `index.html`.** Not `index_chromium.html` — that is the original Chromium page kept for
reference. See [Architecture](./architecture.md).

You need a text editor and nothing else.

## 1. Set the title

Change the placeholder directory name in the `<title>` tag. It becomes the browser tab title
and the page heading.

## 2. Add a row per entry

Copy the shape of the example rows already in the file. Each row carries:

| Column | Notes                                                      |
| ------ | ---------------------------------------------------------- |
| Icon   | `icons/folder.png` for folders, `icons/file.png` for files |
| Name   | The display name, wrapped in the link                      |
| Link   | The `href` — the real path to the file or folder           |
| Size   | Free text                                                  |
| Date   | Free text; nothing computes it                             |

The parent-directory row uses `icons/up.png`.

## 3. Delete the leftovers

The shipped file contains example rows. **Delete every row you did not customise**, or your
listing advertises files that do not exist.

Nothing checks this. Every row is hand-written, so no link is validated and no date is
verified.

## 4. Publish

Copy `index.html` and the `icons/` folder to your server. See [Deployment](./deployment.md).

## Changing the look

Styling is inline in `index.html` by default. To move it into an external stylesheet, or to
swap the icons, see [Configuration](./configuration.md).

## What it does not do

It does not read a directory. Nothing scans a folder and generates rows — the listing is
whatever you typed, and it goes stale the moment the real directory changes.

The original `index_chromium.html` _does_ build its listing dynamically, which is why the
feature list mentions automatic generation. That is the Chromium page, not the simplified one.
