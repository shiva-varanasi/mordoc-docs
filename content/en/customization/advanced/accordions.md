---
title: Accordions
description: Style the collapsible sections you place inside an article's body text.
---

Accordion and Accordions are components you place inside an article's body text. See [Accordions](/writing-content/accordions) for the Markdown syntax. This page covers their appearance.

## Open the override file

```text
config/styles/accordion.css
```

## Tokens

{% table %}
* Token
* What it controls
---
* `--accordion-bg`
* Background of the header and body. Defaults to `--color-bg`.
---
* `--accordion-border`
* Border color of the whole box for a standalone accordion, the divider between items in a group. Defaults to `--color-border`.
---
* `--accordion-radius`
* Corner radius of a standalone accordion, and of the group box wrapping several.
---
* `--accordion-shadow`
* Drop shadow of a standalone accordion, and of the group box wrapping several.
---
* `--accordion-title-color`
* Header text color. Defaults to `--color-fg`.
---
* `--accordion-content-color`
* Body text color. Defaults to `--color-content-fg`.
---
* `--accordion-chevron-color`
* Color of the expand/collapse chevron icon. Defaults to `--color-fg-muted`.
---
* `--accordion-hover-bg`
* Header background on hover.
{% /table %}

## Example accordion.css

A `config/styles/accordion.css` that sets every token on this page, for both light and dark mode:

```css
:root {
  --accordion-bg: #ffffff;
  --accordion-border: #e5e5e5;
  --accordion-radius: 10px;
  --accordion-shadow: 0 1px 3px rgba(0, 0, 0, 0.06), 0 1px 2px rgba(0, 0, 0, 0.04);
  --accordion-title-color: #1c1c1c;
  --accordion-content-color: #3f3f3f;
  --accordion-chevron-color: #6b7280;
  --accordion-hover-bg: #f5f5f5;
}

.dark {
  --accordion-bg: #161616;
  --accordion-border: #2e2e2e;
  --accordion-title-color: #ebebeb;
  --accordion-content-color: #c7c7c7;
  --accordion-chevron-color: #9e9e9e;
  --accordion-hover-bg: #1f1f1f;
}
```

## Next step

- [Style cards and card grids](/customization/advanced/cards).
