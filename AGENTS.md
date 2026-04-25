# AGENTS.md

Guidance for future Codex sessions working on this Jekyll site.

## Project

This repository builds the public website for `janclemenslab.org`.

- Static site generator: Jekyll 4
- Ruby version: `3.3` from `.ruby-version`
- Default branch and GitHub Pages source: `master`
- CI build: `.github/workflows/site.yml`

## Build And Verify

Use the Homebrew Ruby 3.3 toolchain when running commands locally:

```sh
export PATH="/opt/homebrew/opt/ruby@3.3/bin:$PATH"
```

Without that path prefix, macOS may resolve `/usr/bin/ruby` 2.6 and fail to find the Bundler version from `Gemfile.lock`.

Install dependencies:

```sh
bundle install
```

Run a local preview:

```sh
bundle exec jekyll serve --host 127.0.0.1 --port 4000
```

The local preview is expected at `http://127.0.0.1:4000`.

Production build check:

```sh
JEKYLL_ENV=production bundle exec jekyll build --strict_front_matter
```

Always run before finishing changes:

```sh
git diff --check
JEKYLL_ENV=production bundle exec jekyll build --strict_front_matter
```

The Sass compiler currently emits `@import` deprecation warnings. These are expected unless the task is specifically to migrate Sass modules. The build should still exit successfully.

## Important Files

- `_config.yml`: site metadata and Jekyll configuration.
- `_layouts/default.html`: shared HTML shell, header, page hero, metadata.
- `_data/nav.yml`: top navigation labels and paths.
- `_sass/_style.scss`: main visual system and page-specific styles.
- `_sass/vars.scss`, `_sass/typography.scss`, `_sass/tables.scss`: supporting styles.
- `index.md`: home/research landing page.
- `research.md`: detailed research page.
- `people.md`: lab members and openings.
- `publications.md`: renderer for publication data. Do not hand-edit publication entries here.
- `_data/publications.yml`: source of truth for publications.
- `_includes/publication.html`: publication entry renderer.
- `code_data.md`: software and data tools page.
- `contact.md`: contact/address page.
- `img/`: public images and generated assets.

## Content Rules

Keep changes surgical. Prefer editing the relevant Markdown or YAML source instead of generated output. Never edit `_site/`; it is build output.

Use `relative_url` for internal site paths in templates. For local PDFs and assets in data files, prefer root-relative paths such as `/pdf/example.pdf`; the publication include converts root-relative resource links through `relative_url`.

Avoid adding new frameworks or client-side JavaScript unless a task clearly requires it. This site should remain a simple static Jekyll site.

## Publications

Publications live in `_data/publications.yml`, newest first. Each entry should use this shape:

```yaml
- year: 2025
  authors: >-
    __Jan Clemens__, Coauthor Name
  title: >-
    Example publication title with _italic species names_
  citation: >-
    __2025__, Journal Name
  citation_url: "https://doi.org/example"
  links:
    - label: >-
        pdf
      url: "/pdf/example.pdf"
    - label: >-
        preprint
      url: "https://www.biorxiv.org/content/example"
    - label: >-
        code
      url: "https://github.com/janclemenslab/example"
```

Notes:

- Markdown is supported in `authors`, `title`, and `citation`.
- `citation_url` is optional.
- `links` is optional.
- Common link labels are `pdf`, `preprint`, `code`, `code and data`, `documentation and code`, `press`, and `preview`.
- The renderer infers preprint source labels such as `bioRxiv preprint` and `PeerJ preprint` from URLs.
- Do not duplicate publication entries in `publications.md`; it only groups and renders the data.

## Styling

The design is intentionally minimal:

- Light background, restrained accent color, no decorative cards for page sections.
- Header is sticky.
- Page sections should be readable and simple.
- Use existing classes before adding new style patterns.
- Keep cards limited to repeated items or genuinely framed resources.
- Avoid large visual redesigns when the task is a content update.

When changing layout or typography, check at least:

- `/`
- `/research`
- `/people`
- `/publications`
- `/code_data`
- `/contact`

## Git Workflow

Before editing, check:

```sh
git status --short --branch
```

Do not revert user changes. If unrelated files are dirty, leave them alone unless the user asks to include all current changes.

Use branches with the `codex/` prefix for new PR work. If a previous PR branch has already been merged, create a fresh follow-up branch from current `master`.

Typical publish flow:

```sh
git add <files>
git commit -m "Short descriptive message"
git push -u origin <branch>
```

Open PRs against `master`. Use a draft PR for exploratory visual work; use a ready PR for straightforward content fixes unless the user asks otherwise.

## External Links And Facts

For current institutional contact details, software URLs, publication status, or other facts that may change, verify against primary sources before updating the site. Prefer official university pages, project repositories, DOI pages, and journal/preprint pages.
