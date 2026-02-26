---
layout: default
title: Reference
---

# Reference

*Version: February 26, 2026. Reference V1*

---

## Front Matter

Every page starts with a YAML front matter block enclosed in `---`. The fields used by this template are:

| Field       | Required | Description                               |
|-------------|----------|-------------------------------------------|
| `layout`    | Yes      | Always `default` for this template        |
| `title`     | Yes      | Page title shown in the browser tab       |

Example:

```yaml
---
layout: default
title: My Page
---
```

## Adding Pages

1. Create a new `.md` file in the project root (e.g. `guide.md`)
2. Add front matter with `layout: default` and a `title`
3. Register the page in [`_data/nav.yml`](./_data/nav.yml):

```yaml
- title: Section Name
  pages:
    - title: My Page
      url: /guide/
```

Jekyll derives the URL from the file name when `permalink: pretty` is set in `_config.yml`. A file named `guide.md` becomes `/guide/`.

---

## Callout Reference

Quick reference for all four callout variants. See the [Introduction](/) for full usage examples.

| Class             | Icon | Use for                             |
|-------------------|------|-------------------------------------|
| `callout-note`    | ℹ   | General information, tips           |
| `callout-tip`     | ✓   | Best practices, recommended actions |
| `callout-warning` | ⚠   | Things to be careful about          |
| `callout-danger`  | ✕   | Destructive actions, errors         |

---

## Configuration

All site-wide settings live in [`_config.yml`](./_config.yml):

```yaml
title: Simple Documentation
description: Description
baseurl: ""
url: ""
markdown: kramdown
kramdown:
  toc_levels: 1..3
  math_engine: mathjax
permalink: pretty
```

`toc_levels: 1..3` controls which heading levels appear in the sidebar table of contents.

---

*End of document.*
