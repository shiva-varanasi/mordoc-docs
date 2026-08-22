---
title: Callouts
description: Style the four callout types you use to highlight notes, tips, warnings, and dangers in Markdown content.
---

Callouts are one of the components you place inside an article's body text. See [Callouts](/writing-content/callouts) for the Markdown syntax. This page covers their appearance, driven by the `type` attribute: `note`, `tip`, `warning`, or `danger`.

## Open the override file

```text
config/styles/callout.css
```

## Tokens

{% table %}
* Token
* What it controls
---
* `--callout-radius`
* Corner radius, shared by all four types.
---
* `--callout-note-accent`
* Left border and icon color for `type="note"`.
---
* `--callout-tip-accent`
* Left border and icon color for `type="tip"`.
---
* `--callout-warning-accent`
* Left border and icon color for `type="warning"`.
---
* `--callout-danger-accent`
* Left border and icon color for `type="danger"`.
---
* `--callout-note-bg`
* Background tint for `type="note"`.
---
* `--callout-tip-bg`
* Background tint for `type="tip"`.
---
* `--callout-warning-bg`
* Background tint for `type="warning"`.
---
* `--callout-danger-bg`
* Background tint for `type="danger"`.
---
* `--callout-title-color`
* Title text color, shared by all four types.
---
* `--callout-body-color`
* Body text color, shared by all four types.
{% /table %}

## Example callout.css

A `config/styles/callout.css` that sets every token on this page, for both light and dark mode. The accent colors themselves stay the same in both modes; only the background tints and text colors need re-tuning:

```css
:root {
  --callout-radius: 6px;
  --callout-note-accent: #47a3d1;
  --callout-warning-accent: #e6911a;
  --callout-danger-accent: #d22d2d;
  --callout-tip-accent: #0d9488;
  --callout-note-bg: color-mix(in oklch, #47a3d1 8%, white);
  --callout-warning-bg: color-mix(in oklch, #e6911a 8%, white);
  --callout-danger-bg: color-mix(in oklch, #d22d2d 8%, white);
  --callout-tip-bg: color-mix(in oklch, #0d9488 8%, white);
  --callout-title-color: #0f172a;
  --callout-body-color: #475569;
}

.dark {
  --callout-note-bg: color-mix(in oklch, #47a3d1 10%, #1a1a1a);
  --callout-warning-bg: color-mix(in oklch, #e6911a 10%, #1a1a1a);
  --callout-danger-bg: color-mix(in oklch, #d22d2d 10%, #1a1a1a);
  --callout-tip-bg: color-mix(in oklch, #0d9488 12%, #1a1a1a);
  --callout-title-color: #f1f5f9;
  --callout-body-color: #94a3b8;
}
```

## Next step

- [Style cards and card grids](/customization/advanced/cards).
