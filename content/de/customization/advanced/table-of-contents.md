---
title: Inhaltsverzeichnis
description: Gestalten Sie die Links zu den Überschriften auf der Seite, die in der TOC-Spalte eines Artikels angezeigt werden.
---

Table of Contents wird innerhalb von Contents TOC-Spalte gerendert (siehe [Inhalts-Layout](/de/customization/advanced/content-layout)): die Liste der Überschriften auf der Seite, zu denen ein Leser springen kann.

## Die Override-Datei öffnen

```text
config/styles/toc.css
```

## Tokens

{% table %}
* Token
* Was es steuert
---
* `--toc-link-hover-fg`
* Textfarbe eines Überschriften-Links bei Hover.
---
* `--toc-link-active-fg`
* Textfarbe des Überschriften-Links, der der aktuellen Scrollposition des Lesers entspricht.
---
* `--toc-link-active-border`
* Farbe des linken Rands, der den aktiven Überschriften-Link markiert.
{% /table %}

## Beispiel toc.css

Eine `config/styles/toc.css`, die jeden Token auf dieser Seite festlegt, für Hell- und Dunkelmodus:

```css
:root {
  --toc-link-hover-fg: #0f766e;
  --toc-link-active-fg: #0f766e;
  --toc-link-active-border: #0f766e;
}

.dark {
  --toc-link-hover-fg: #2dd4bf;
  --toc-link-active-fg: #2dd4bf;
  --toc-link-active-border: #2dd4bf;
}
```

## Nächster Schritt

- [Callouts gestalten](/de/customization/advanced/callouts).
