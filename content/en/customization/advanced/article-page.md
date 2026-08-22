---
title: Article Page
description: Style the breadcrumb, blockquote, and inline code chip on an article page.
---

Article Page renders inside Content's article column (see [Content Layout](/customization/advanced/content-layout)): the breadcrumb, title, description, and the body content rendered from your Markdown.

Most of the body text (headings, paragraphs, links, lists, tables) already looks right from the global tokens in [Design Tokens](/customization/advanced/design-tokens) (`--color-fg`, `--color-content-fg`, `--color-border`) and doesn't need its own tokens. Only the breadcrumb, blockquotes, and the inline code chip have article-specific tokens of their own.

## Open the override file

```text
config/styles/article-page.css
```

## Tokens

{% table %}
* Token
* What it controls
---
* `--breadcrumb-link`
* Text color of a breadcrumb segment that links to a parent page.
---
* `--breadcrumb-link-hover`
* That segment's color on hover.
---
* `--breadcrumb-current`
* Text color of the current page's breadcrumb segment (not a link).
---
* `--breadcrumb-sep`
* Color of the `›` separator between breadcrumb segments.
---
* `--blockquote-radius`
* Corner radius of a Markdown `>` blockquote.
---
* `--inline-code-radius`
* Corner radius of inline `` `code` `` in body text.
{% /table %}

## Example article-page.css

A `config/styles/article-page.css` that sets every token on this page, for both light and dark mode:

```css
:root {
  --breadcrumb-link: #6b6b6b;
  --breadcrumb-link-hover: #1c1c1c;
  --breadcrumb-current: #111827;
  --breadcrumb-sep: #6b6b6b;
  --blockquote-radius: 6px;
  --inline-code-radius: 4px;
}

.dark {
  --breadcrumb-link: #a0a0a0;
  --breadcrumb-link-hover: #eaeaea;
  --breadcrumb-current: #f3f4f6;
}
```

## Next step

- [Style the table of contents](/customization/advanced/table-of-contents).
