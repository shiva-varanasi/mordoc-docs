---
title: Table of Contents
description: Style the on-page heading links shown in the TOC column of an article.
---

Table of Contents renders inside Content's TOC column (see [Content Layout](/customization/advanced/content-layout)): the list of on-page headings a reader can jump to.

## Open the override file

```text
config/styles/toc.css
```

## Tokens

{% table %}
* Token
* What it controls
---
* `--toc-link-hover-fg`
* Text color of a heading link on hover.
---
* `--toc-link-active-fg`
* Text color of the heading link matching the reader's current scroll position.
---
* `--toc-link-active-border`
* Color of the left border marking the active heading link.
{% /table %}

## Example toc.css

A `config/styles/toc.css` that sets every token on this page, for both light and dark mode:

```css
:root {
  --toc-link-hover-fg: #0f766e;
  --toc-link-active-fg: #0f766e;
  --toc-link-active-border: #0f766e;
}

.dark {
  --toc-link-hover-fg: #2dd4bf;
  --toc-link-active-fg: #2dd4bf;
  --toc-link-active-border: #2dd4bf;
}
```

## Next step

- [Style callouts](/customization/advanced/callouts).
