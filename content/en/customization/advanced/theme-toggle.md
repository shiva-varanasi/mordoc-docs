---
title: Theme Toggle
description: Style the light/dark mode switch shown in the header.
---

`config/styles/theme-toggle.css` styles the button readers use to switch between light and dark mode.

## Open the override file

```text
config/styles/theme-toggle.css
```

## Tokens

{% table %}
* Token
* What it controls
---
* `--theme-toggle-size`
* Width and height of the button.
---
* `--theme-toggle-radius`
* Corner radius of the button.
---
* `--theme-toggle-icon-size`
* Size of the sun/moon icon inside the button.
---
* `--theme-toggle-bg`
* Button background.
---
* `--theme-toggle-bg-hover`
* Button background on hover.
---
* `--theme-toggle-border`
* Button border color.
---
* `--theme-toggle-fg`
* Icon color.
{% /table %}

## Example theme-toggle.css

A `config/styles/theme-toggle.css` that sets every token on this page, for both light and dark mode:

```css
:root {
  --theme-toggle-size: 40px;
  --theme-toggle-radius: 999px;
  --theme-toggle-icon-size: 20px;
  --theme-toggle-bg: #ffffff;
  --theme-toggle-bg-hover: #f5f5f5;
  --theme-toggle-border: #e5e5e5;
  --theme-toggle-fg: #1c1c1c;
}

.dark {
  --theme-toggle-bg: #161616;
  --theme-toggle-bg-hover: #242424;
  --theme-toggle-border: #333333;
  --theme-toggle-fg: #ebebeb;
}
```

## Next step

- [Style search](/customization/advanced/search).
