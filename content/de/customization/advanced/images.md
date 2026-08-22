---
title: Bilder
description: Gestalten Sie die Inline-Abbildung und die zoombare Lightbox für Bilder, die in Markdown-Inhalten platziert werden.
---

Image umschließt ein Standard-Markdown-`![]()`-Bild mit einer Bildunterschrift und einer Klick-zum-Zoomen-Lightbox. Siehe [Bilder](/de/writing-content/images) für die Markdown-Syntax. Diese Seite behandelt sein Erscheinungsbild.

## Die Override-Datei öffnen

```text
config/styles/image.css
```

## Tokens

{% table %}
* Token
* Was es steuert
---
* `--image-radius`
* Eckenradius, gemeinsam für die Inline-Abbildung und das Lightbox-Bild.
---
* `--image-caption-color`
* Textfarbe der Bildunterschrift unter der Inline-Abbildung. Standardmäßig `--color-fg-muted`.
---
* `--image-overlay-bg`
* Hintergrund hinter der Vollbild-Lightbox.
---
* `--image-close-button-radius`
* Eckenradius des Schließen-Buttons der Lightbox.
{% /table %}

## Beispiel image.css

Eine `config/styles/image.css`, die jeden Token auf dieser Seite festlegt, für Hell- und Dunkelmodus:

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

## Nächster Schritt

- [Den Hero gestalten](/de/customization/advanced/hero).
