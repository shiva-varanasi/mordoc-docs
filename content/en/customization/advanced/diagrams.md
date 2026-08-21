---
title: Diagrams
description: Style the canvas, lightbox, and participant colors used by Mordoc's diagrams.
---

This page covers diagram appearance. For the Markdown syntax used to draw a diagram, see [Diagrams](/creating-diagrams/overview) instead.

## Open the override file

```text
config/styles/diagram.css
```

## Canvas and controls

{% table %}
* Token
* What it controls
---
* `--diagram-grid-spacing`
* Spacing of the dotted grid drawn behind every diagram.
---
* `--diagram-grid-dot`
* The dotted-grid background image itself. Defaults to a radial gradient using `--color-border`.
---
* `--diagram-radius`
* Corner radius of the inline diagram figure.
---
* `--diagram-overlay-bg`
* Backdrop behind the full-screen lightbox.
---
* `--diagram-lightbox-radius`
* Corner radius of the lightbox panel.
---
* `--diagram-button-radius`
* Corner radius of the lightbox's close button and zoom-controls pill.
---
* `--diagram-zoom-button-radius`
* Corner radius of the `+`/`−` buttons inside the zoom-controls pill.
{% /table %}

## Diagram ink

These color the diagram's own drawing: labels, lifelines, arrows, and up to eight participant colors. Today only sequence diagrams use them, but they're shared primitives any future diagram type can draw from too.

{% table %}
* Token
* What it controls
---
* `--diagram-label`
* Text color for labels. Tracks `--color-fg`, so there's usually no need to set it separately.
---
* `--diagram-label-bg`
* Background behind a label, erasing the dotted grid locally. Tracks `--color-surface`.
---
* `--diagram-lifeline`
* Color of a participant's vertical lifeline.
---
* `--diagram-arrow`
* Color of message arrows between participants.
---
* `--diagram-activation-1` … `--diagram-activation-8`
* Eight participant colors, assigned in order as participants appear in the diagram.
{% /table %}

## Example diagram.css

A `config/styles/diagram.css` that sets every token on this page, for both light and dark mode:

```css
:root {
  --diagram-grid-spacing: 20px;
  --diagram-grid-dot: radial-gradient(circle, #e5e5e5 1px, transparent 1px);
  --diagram-radius: 6px;
  --diagram-overlay-bg: rgba(0, 0, 0, 0.82);
  --diagram-lightbox-radius: 8px;
  --diagram-button-radius: 6px;
  --diagram-zoom-button-radius: 4px;

  --diagram-label: #1c1c1c;
  --diagram-label-bg: #fafafa;
  --diagram-lifeline: #757575;
  --diagram-arrow: #52514e;
  --diagram-activation-1: #2563eb;
  --diagram-activation-2: #16a34a;
  --diagram-activation-3: #db2777;
  --diagram-activation-4: #ca8a04;
  --diagram-activation-5: #0d9488;
  --diagram-activation-6: #ea580c;
  --diagram-activation-7: #6d28d9;
  --diagram-activation-8: #dc2626;
}

.dark {
  --diagram-grid-dot: radial-gradient(circle, #2e2e2e 1px, transparent 1px);
  --diagram-label: #ebebeb;
  --diagram-label-bg: #161616;
  --diagram-lifeline: #4f4e46;
  --diagram-arrow: #b0afaa;
  --diagram-activation-1: #60a5fa;
  --diagram-activation-2: #4ade80;
  --diagram-activation-3: #f472b6;
  --diagram-activation-4: #facc15;
  --diagram-activation-5: #2dd4bf;
  --diagram-activation-6: #fb923c;
  --diagram-activation-7: #a78bfa;
  --diagram-activation-8: #f87171;
}
```

## Next step

- [Style images](/customization/advanced/images).
