# MiscellaneousNotes

Personal technical notes and code snippets, published as a static site via [Jekyll](https://jekyllrb.com/) on [GitHub Pages](https://pages.github.com/).

Live site: **https://ajw170.github.io/MiscellaneousNotes**

---

## How the site works

This is a minimal [Jekyll](https://jekyllrb.com/) site using the [minima](https://github.com/jekyll/minima) theme. Jekyll reads Markdown files, applies Liquid templates, and generates a static HTML site that GitHub Pages hosts automatically.

### Collections

There are two content types, each stored in its own directory:

| Type | Directory | URL pattern | Layout |
|---|---|---|---|
| **Notes** | `_notes/` | `/notes/<filename>/` | `_layouts/note.html` |
| **Snippets** | `_snippets/` | `/snippets/<filename>/` | `_layouts/snippet.html` |

**Notes** are longer-form writeups: command references, how-tos, tips and tricks.

**Snippets** are short, self-contained code blocks — a single function, idiom, or pattern worth saving.

### Adding a note

Create a `.md` file in `_notes/`:

```markdown
---
title: "Docker Networking Cheatsheet"
date: 2026-07-01
tags: [docker, networking]
---

## Bridge networks

...content here...
```

### Adding a snippet

Create a `.md` file in `_snippets/`:

```markdown
---
title: "Flatten a Nested List (Python)"
date: 2026-07-01
language: Python
tags: [python, lists]
---

Brief description of what this does.

\`\`\`python
def flatten(lst):
    return [x for sub in lst for x in sub]
\`\`\`
```

The optional `language` field appears on the index page next to the title.

### Front matter fields

| Field | Required | Description |
|---|---|---|
| `title` | Yes | Displayed as the page heading and on the index |
| `date` | Recommended | Used for sorting on the index (`YYYY-MM-DD`) |
| `tags` | Optional | List of tags shown in brackets on the index |
| `language` | Optional (snippets) | Programming language label |

---

## Running locally

### Prerequisites

- Ruby ≥ 3.1 (`ruby --version`)
- Bundler (`gem install bundler`)

### Setup

```bash
# Clone the repo (if you haven't already)
git clone https://github.com/ajw170/MiscellaneousNotes.git
cd MiscellaneousNotes

# Install dependencies
bundle install
```

### Serve

```bash
bundle exec jekyll serve
```

The site is available at **http://localhost:4000/MiscellaneousNotes**.

Jekyll watches for file changes and rebuilds automatically. Press `Ctrl+C` to stop.

### Build only (no server)

```bash
bundle exec jekyll build
# Output goes to _site/
```

---

## Enabling GitHub Pages

In the repository on GitHub:

1. Go to **Settings → Pages**
2. Under **Source**, select **Deploy from a branch**
3. Choose branch **`main`**, folder **`/ (root)`**
4. Click **Save**

GitHub will build and deploy the site automatically on every push to `main`.

---

## File structure

```
.
├── _config.yml          # Jekyll site configuration
├── _layouts/
│   ├── note.html        # Layout for note pages
│   └── snippet.html     # Layout for snippet pages
├── _notes/              # Long-form notes (Markdown)
├── _snippets/           # Short code snippets (Markdown)
├── index.md             # Homepage (lists all notes and snippets)
├── Gemfile              # Ruby dependencies (github-pages gem)
└── .gitignore           # Excludes _site/, .jekyll-cache/, vendor/
```
