---
title: Sections
description: Style the default background for section blocks on landing pages.
---

Section groups content on a landing page. See [Landing Pages](/writing-content/landing-pages) for the Markdown syntax. It has a single site-wide token; everything else (title and body text color) already comes from the global tokens in [Design Tokens](/customization/advanced/design-tokens).

## Open the override file

```text
config/styles/section.css
```

## Tokens

{% table %}
* Token
* What it controls
---
* `--section-bg`
* Solid background color, used when a section has no `background` image. Transparent by default.
{% /table %}

```css
:root {
  --section-bg: #f8fafc;
}
```

## Example section.css

A `config/styles/section.css` for both light and dark mode:

```css
:root {
  --section-bg: #f8fafc;
}

.dark {
  --section-bg: #0f172a;
}
```

## Next step

- [Style buttons](/customization/advanced/buttons).
