---
title: Header
description: Style the header's own spacing, logo size, and hamburger button, independent of what's inside it.
---

The Header Area box (from [App Layout](/customization/advanced/app-layout)) contains the Header component. Header draws its own two-row skeleton inside that box:

```text
┌─────────────────────────────────────────────────────────────┐
│ [Logo]           [        Search        ]      [Actions]    │  primary row
├─────────────────────────────────────────────────────────────┤
│  Link   Link   Link                                         │  top navigation row
└─────────────────────────────────────────────────────────────┘
```

* **Primary row**: a logo on the left, search centered, and actions (header links, language picker, theme toggle) on the right. Below 768px, search and the right-side actions collapse behind a hamburger button.
* **Top navigation row**: only present when your project uses `config/navigation/topnav.yaml` instead of a single sidenav. See [Top Navigation](/customization/advanced/top-navigation) for its own tokens.

This page covers Header's own spacing and the logo/hamburger. Header links, the language picker, the theme toggle, and search each have their own page, linked at the bottom.

## Open the override file

```text
config/styles/header.css
```

## Tokens

{% table %}
* Token
* What it controls
---
* `--header-padding`
* Horizontal padding on both rows. Defaults to `16px`.
---
* `--primary-area-gap`
* Gap between the logo, search, and actions in the primary row. Grows at wider breakpoints by default; setting this overrides all of them to one fixed value.
---
* `--brand-logo-size`
* Height of the logo image.
---
* `--menu-btn-size`
* Width and height of the mobile hamburger/close button.
---
* `--menu-btn-radius`
* Corner radius of the mobile hamburger/close button.
---
* `--menu-btn-icon`
* Size of the hamburger/close icon inside the button.
{% /table %}

```css
:root {
  --brand-logo-size: 32px;
  --menu-btn-radius: 10px;
}
```

## Example header.css

A `config/styles/header.css` that sets every token on this page. None of them are colors, so there's no separate dark-mode variant to set:

```css
:root {
  --header-padding: 20px;
  --primary-area-gap: 16px;
  --brand-logo-size: 32px;
  --menu-btn-size: 40px;
  --menu-btn-radius: 10px;
  --menu-btn-icon: 22px;
}
```

## Next step

- [Style header links](/customization/advanced/header-links).
