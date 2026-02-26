# Simple Documentation

A minimal, single-layout Jekyll documentation theme. Write pages in Markdown, configure navigation in one YAML file, and get a polished site with no build tooling beyond Jekyll.

---

## Features

- **Dark / light theme** — toggle in the topbar, preference persisted in `localStorage`
- **Sidebar navigation** — defined in `_data/nav.yml`; active page highlighted automatically
- **Table of contents** — auto-built from `h1`–`h3` headings with scroll-spy
- **Heading anchor links** — hover any heading to reveal a copyable `#` deep-link
- **In-page search** — highlights all matches; `Enter` / `Shift+Enter` to cycle, `Esc` to clear
- **Code copy button** — appears on hover over every fenced code block
- **Prev / Next pagination** — automatic from nav order
- **Reading progress bar** — thin accent bar fixed to the top of the viewport
- **Callout blocks** — four variants: note, tip, warning, danger
- **LaTeX / math** — via MathJax 3
- **Print stylesheet** — hides UI chrome, expands prose to full width
- **Works without a server** — all internal links are rewritten for `file://` browsing

---

## Quick Start

**Requirements:** Ruby + Bundler

```bash
bundle install
bundle exec jekyll serve
# → http://localhost:4000
```

Open `_site/index.html` directly in a browser if you prefer to skip the server — all links and assets resolve correctly via `file://`.

---

## Adding Pages

1. Create `my-page.md` in the project root:

```yaml
---
layout: default
title: My Page
---

# My Page
Content here.
```

2. Register it in `_data/nav.yml`:

```yaml
- title: Section Name
  pages:
    - title: My Page
      url: /my-page/
```

With `permalink: pretty` (default), `my-page.md` is served at `/my-page/`.

---

## Callout Blocks

Add a raw HTML `<div>` with `markdown="1"` so Jekyll processes the inner text:

```html
<div class="callout callout-note" markdown="1">
**Note:** Supports _markdown_, `code`, and [links](/).
</div>
```

| Class             | Icon | Use for                        |
|-------------------|------|--------------------------------|
| `callout-note`    | ℹ   | General info                   |
| `callout-tip`     | ✓   | Best practices                 |
| `callout-warning` | ⚠   | Non-critical cautions          |
| `callout-danger`  | ✕   | Destructive / breaking actions |

---

## Disabling the Reading Progress Bar

Remove two things from [`_layouts/default.html`](_layouts/default.html):

1. `<div id="reading-progress" aria-hidden="true"></div>` — near the top of `<body>`
2. The JS block between `// ── Reading progress bar` and `// ── End reading progress bar`

---

## Project Structure

```
.
├── _data/
│   └── nav.yml          # Page navigation order
├── _layouts/
│   └── default.html     # Single layout (HTML + CSS + JS)
├── assets/
│   └── css/
│       └── style.css    # All styles (light + dark theme)
├── _config.yml          # Site title, description, kramdown settings
└── index.md             # Root page (copy to add more pages)
```

---

## Configuration

Edit `_config.yml`:

```yaml
title: Simple Documentation
description: Your tagline here
```

All other settings (`permalink: pretty`, `markdown: kramdown`, MathJax) can stay as-is.

---

## License

MIT
