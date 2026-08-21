---
title: Images
description: Style the inline figure and zoomable lightbox for images placed in Markdown content.
---

Image wraps a standard Markdown `![]()` image with a caption and a click-to-zoom lightbox. See [Images](/writing-content/images) for the Markdown syntax. This page covers its appearance.

## Open the override file

```text
config/styles/image.css
```

## Tokens

{% table %}
* Token
* What it controls
---
* `--image-radius`
* Corner radius, shared by the inline figure and the lightbox image.
---
* `--image-caption-color`
* Caption text color under the inline figure. Defaults to `--color-fg-muted`.
---
* `--image-overlay-bg`
* Backdrop behind the full-screen lightbox.
---
* `--image-close-button-radius`
* Corner radius of the lightbox's close button.
{% /table %}

## Example image.css

A `config/styles/image.css` that sets every token on this page, for both light and dark mode:

```css
:root {
  --image-radius: 4px;
  --image-caption-color: #6b7280;
  --image-overlay-bg: rgba(0, 0, 0, 0.82);
  --image-close-button-radius: 6px;
}

.dark {
  --image-caption-color: #9ca3af;
}
```

## Next step

- [Style the hero](/customization/advanced/hero).
