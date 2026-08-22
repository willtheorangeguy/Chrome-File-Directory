# Known Issues — Chrome-File-Directory

Concrete defects and gaps found while writing this repository's documentation in
August 2026. **Nothing here was changed** — each one needs a code, configuration, or
licensing decision rather than a documentation one.

Ordered by severity. See [`docs/roadmap.md`](../roadmap.md) for the narrative version,
which also covers deliberate non-goals.

**3 open:** 1 medium, 2 low.

## 1. `style.css` references a directory that does not exist

**Severity:** Medium
**Where:** `style.css`

**What:** It references `imgs/file.png`, `imgs/folder.png`, and `imgs/up.png`. The icons ship in **`icons/`**, and there is no `imgs/` directory anywhere in the repository.

**Why it matters:** The documentation actively tells users to copy `style.css` and link it from `index.html`, so anyone following those steps gets every icon broken. The inline styling in `index.html` uses the correct path, which is why this stays hidden until someone opts in. `CLAUDE.md` had already noticed and recorded it as a note.

**Suggested fix:** One line, either direction: point the stylesheet at `icons/`, or add an `imgs/` directory.

## 2. The Docker workflow filename is misspelled

**Severity:** Low
**Where:** `.github/workflows/docker-pubish.yml`

**What:** Should be `docker-publish.yml`. It works, because the README badge points at the same misspelled name.

**Why it matters:** Differs from the Apache and Nginx siblings; anyone looking for `docker-publish.yml` will not find it.

**Suggested fix:** Rename it and update the badge in the same commit.

## 3. Example rows ship live rather than commented out

**Severity:** Low
**Where:** `index.html`

**What:** Forgetting to delete them leaves a listing advertising files that do not exist, and nothing warns you.

**Why it matters:** The most common user error with this project.

**Suggested fix:** Ship them commented out.

---

## Also, across every repository

**`.bandit` is present on disk but untracked in git.** Verified in PyWorkout, treklogger,
skyscanner-cli, booking-cli, piggy, and aibot — the config file exists locally in each but
`git ls-files` does not know about it, so none of it reached GitHub.

The August 2026 security sweep therefore looks complete locally and landed nowhere. Worth
checking across all 44 repositories it covered.
