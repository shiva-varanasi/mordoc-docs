---
title: Buttons
description: Style the primary and secondary button variants used on landing pages and in the header.
---

Button renders wherever the `{% button %}` tag is used. See [Landing Pages](/writing-content/landing-pages) for the Markdown syntax. It has two variants, `primary` and `secondary`, each with its own tokens.

## Open the override file

```text
config/styles/button.css
```

## Shared shape

{% table %}
* Token
* What it controls
---
* `--button-height`
* Height of the button, both variants.
---
* `--button-padding`
* Horizontal padding, both variants.
---
* `--button-font-size`
* Font size, both variants.
---
* `--button-radius`
* Corner radius, both variants.
---
* `--button-shadow`
* Drop shadow at rest. `none` by default; set it for a theme whose button color is close to its background, so the button still reads as a distinct shape.
---
* `--button-shadow-hover`
* Drop shadow on hover.
{% /table %}

## Primary variant

{% table %}
* Token
* What it controls
---
* `--button-primary-bg`
* Background. Defaults to `--accent`.
---
* `--button-primary-border`
* Border color. Defaults to `--accent`.
---
* `--button-primary-fg`
* Text color. White by default.
---
* `--button-primary-hover-bg`
* Background on hover.
---
* `--button-primary-hover-border`
* Border color on hover.
{% /table %}

## Secondary variant

{% table %}
* Token
* What it controls
---
* `--button-secondary-fg`
* Text color. Defaults to `--accent`.
---
* `--button-secondary-hover-bg`
* Background on hover.
{% /table %}

{% callout type="note" title="Header Links reuses these same tokens" %}
A header link configured as a button (see [Header Links](/customization/advanced/header-links)) renders through this same component, just at a smaller height/padding/font-size set locally by that file. Changing the colors here changes both places at once.
{% /callout %}

## Example button.css

A `config/styles/button.css` that sets every token on this page, for both light and dark mode:

```css
:root {
  --button-height: 2.625rem;
  --button-padding: 1.375rem;
  --button-font-size: 0.9375rem;
  --button-radius: 999px;
  --button-shadow: none;
  --button-shadow-hover: none;

  --button-primary-bg: #0d9488;
  --button-primary-border: #0d9488;
  --button-primary-fg: #ffffff;
  --button-primary-hover-bg: #0f766e;
  --button-primary-hover-border: #0f766e;

  --button-secondary-fg: #0d9488;
  --button-secondary-hover-bg: #f0fdfa;
}

.dark {
  --button-primary-bg: #2dd4bf;
  --button-primary-border: #2dd4bf;
  --button-primary-fg: #0f172a;
  --button-primary-hover-bg: #5eead4;
  --button-primary-hover-border: #5eead4;

  --button-secondary-fg: #2dd4bf;
  --button-secondary-hover-bg: #0f2e2b;
}
```

You've now covered every part of Mordoc's UI. From here, get your site live:

## Next step

- [Build your site](/publishing/build-your-site).
