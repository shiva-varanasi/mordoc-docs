---
title: Top Navigation
description: Style the second header row shown when a project uses per-area top navigation.
---

This page is about **appearance**: `config/styles/topnav.css`. To set up top navigation itself, the per-area sections and which sidenav each links to, see [Top Navigation](/configuration/top-navigation) under Configuration instead.

When a project uses `config/navigation/topnav.yaml`, Header renders a second row below the primary one. See [Header](/customization/advanced/header) for where this row sits. Each link fills the row's full height, with a bottom border marking the active one.

## Open the override file

```text
config/styles/topnav.css
```

## Tokens

{% table %}
* Token
* What it controls
---
* `--topnav-link-padding`
* Horizontal padding of each link.
---
* `--topnav-link-font-size`
* Font size of each link.
---
* `--topnav-active-border-width`
* Thickness of the bottom border marking the active link.
---
* `--topnav-active-border-color`
* Color of that border. Defaults to `--accent-emphasis`.
{% /table %}

## Example topnav.css

A `config/styles/topnav.css` that sets every token on this page, for both light and dark mode:

```css
:root {
  --topnav-link-padding: 0.75rem;
  --topnav-link-font-size: 0.875rem;
  --topnav-active-border-width: 3px;
  --topnav-active-border-color: #0f766e;
}

.dark {
  --topnav-active-border-color: #2dd4bf;
}
```

## Next step

- [Style the language picker](/customization/advanced/language-picker).
