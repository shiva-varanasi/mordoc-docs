---
title: Header Links
description: Style the custom links shown in the header, as plain links or buttons.
---

This page is about **appearance**: `config/styles/header-links.css`. To add, remove, or reorder the links themselves, see [Header Links](/configuration/header-links) under Configuration instead.

Header links render in the right side of the header's primary row: as plain underlined links on desktop, or collapsed into a single overflow-menu button below 768px.

## Open the override file

```text
config/styles/header-links.css
```

## Tokens

{% table %}
* Token
* What it controls
---
* `--header-links-link-color`
* Text color of a plain-link header link.
---
* `--header-links-link-color-hover`
* Text color on hover.
---
* `--header-links-link-padding`
* Horizontal padding around a plain-link entry.
---
* `--header-links-link-font-size`
* Font size of a plain-link entry.
---
* `--header-links-link-radius`
* Corner radius of a plain-link entry (visible on its focus ring).
---
* `--header-links-button-height`
* Height of a button-variant header link.
---
* `--header-links-button-padding`
* Horizontal padding of a button-variant header link.
---
* `--header-links-button-font-size`
* Font size of a button-variant header link.
---
* `--header-links-menu-btn-size`
* Width and height of the mobile overflow-menu button (the "⋯" trigger).
---
* `--header-links-menu-btn-radius`
* Corner radius of the mobile overflow-menu button.
---
* `--header-links-dropdown-radius`
* Corner radius of the mobile overflow dropdown panel.
---
* `--header-links-dropdown-item-radius`
* Corner radius of each row inside the mobile overflow dropdown.
---
* `--header-links-dropdown-item-padding`
* Padding of each row inside the mobile overflow dropdown.
---
* `--header-links-dropdown-item-font-size`
* Font size of each row inside the mobile overflow dropdown.
{% /table %}

{% callout type="note" title="Button-variant links reuse Button's tokens" %}
A header link configured as a button doesn't have its own background/border tokens here. It renders using the same tokens as the [Buttons](/customization/advanced/buttons) component, just at the compact height, padding, and font size set above. Change its color by overriding `--button-primary-bg` and friends on the Buttons page.
{% /callout %}

## Example header-links.css

A `config/styles/header-links.css` that sets every token on this page, for both light and dark mode:

```css
:root {
  --header-links-link-color: #0f766e;
  --header-links-link-color-hover: #115e59;
  --header-links-link-padding: 0.25rem;
  --header-links-link-font-size: 0.875rem;
  --header-links-link-radius: 4px;
  --header-links-button-height: 2rem;
  --header-links-button-padding: 0.875rem;
  --header-links-button-font-size: 0.875rem;
  --header-links-menu-btn-size: 40px;
  --header-links-menu-btn-radius: 8px;
  --header-links-dropdown-radius: 8px;
  --header-links-dropdown-item-radius: 6px;
  --header-links-dropdown-item-padding: 0.5rem 0.75rem;
  --header-links-dropdown-item-font-size: 0.875rem;
}

.dark {
  --header-links-link-color: #2dd4bf;
  --header-links-link-color-hover: #5eead4;
}
```

## Next step

- [Style the top navigation](/customization/advanced/top-navigation).
