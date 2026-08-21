---
title: Cards and Card Grids
description: Style the cards you arrange in grids on landing and index-style pages.
---

Cards are one of the components you place inside an article's body text. See [Cards and Card Grids](/writing-content/cards-and-card-grids) for the Markdown syntax. This page covers card appearance.

## Open the override file

```text
config/styles/card.css
```

## Tokens

{% table %}
* Token
* What it controls
---
* `--card-bg`
* Card background. Defaults to `--color-bg`.
---
* `--card-border`
* Card border. Defaults to `--color-border`.
---
* `--card-border-hover`
* Border color on hover, for a card that links somewhere. Defaults to `--accent`.
---
* `--card-radius`
* Corner radius of the whole card.
---
* `--card-shadow`
* Drop shadow at rest.
---
* `--card-shadow-hover`
* Drop shadow on hover, for a linked card.
---
* `--card-title-color`
* Title text color. Defaults to `--color-fg`.
---
* `--card-desc-color`
* Description text color. Defaults to `--color-fg-muted`.
---
* `--card-tag-bg`
* Background of the small tag badge.
---
* `--card-tag-color`
* Text color of the tag badge.
---
* `--card-tag-radius`
* Corner radius of the tag badge.
---
* `--card-arrow-color`
* Color of the trailing arrow on a linked card, before hover.
{% /table %}

```css
:root {
  --card-radius: 14px;
  --card-border-hover: #0d9488;
}
```

Most of these already default to a global token (`--color-bg`, `--accent`, and similar), so changing [Design Tokens](/customization/advanced/design-tokens) shifts cards too, unless you override them here specifically.

## Example card.css

A `config/styles/card.css` that sets every token on this page, for both light and dark mode:

```css
:root {
  --card-bg: #ffffff;
  --card-border: #e5e5e5;
  --card-border-hover: #0d9488;
  --card-radius: 14px;
  --card-shadow: 0 1px 3px rgba(0, 0, 0, 0.06), 0 1px 2px rgba(0, 0, 0, 0.04);
  --card-shadow-hover: 0 4px 6px -1px rgba(0, 0, 0, 0.07), 0 2px 4px -1px rgba(0, 0, 0, 0.04);
  --card-title-color: #1c1c1c;
  --card-desc-color: #6b7280;
  --card-tag-bg: #f0fdfa;
  --card-tag-color: #0f766e;
  --card-tag-radius: 4px;
  --card-arrow-color: #6b7280;
}

.dark {
  --card-bg: #161616;
  --card-border: #2e2e2e;
  --card-border-hover: #2dd4bf;
  --card-title-color: #ebebeb;
  --card-desc-color: #9e9e9e;
  --card-tag-bg: #0f2e2b;
  --card-tag-color: #2dd4bf;
  --card-arrow-color: #9e9e9e;
}
```

## Next step

- [Style code blocks](/customization/advanced/code-blocks).
