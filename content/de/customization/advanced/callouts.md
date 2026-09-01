---
title: Callouts
description: Gestalten Sie die vier Callout-Typen, mit denen Sie Hinweise, Tipps, Warnungen und Gefahren in Markdown-Inhalten hervorheben.
---

Callouts sind eine der Komponenten, die Sie im Fließtext eines Artikels platzieren. Siehe [Callouts](/de/writing-content/callouts) für die Markdown-Syntax. Diese Seite behandelt ihr Erscheinungsbild, gesteuert durch das `type`-Attribut: `note`, `tip`, `warning` oder `danger`.

## Die Override-Datei öffnen

```text
config/styles/callout.css
```

## Tokens

{% table %}
* Token
* Was es steuert
---
* `--callout-radius`
* Eckenradius, gemeinsam für alle vier Typen.
---
* `--callout-note-accent`
* Linker Rand und Icon-Farbe für `type="note"`.
---
* `--callout-tip-accent`
* Linker Rand und Icon-Farbe für `type="tip"`.
---
* `--callout-warning-accent`
* Linker Rand und Icon-Farbe für `type="warning"`.
---
* `--callout-danger-accent`
* Linker Rand und Icon-Farbe für `type="danger"`.
---
* `--callout-note-bg`
* Hintergrundton für `type="note"`.
---
* `--callout-tip-bg`
* Hintergrundton für `type="tip"`.
---
* `--callout-warning-bg`
* Hintergrundton für `type="warning"`.
---
* `--callout-danger-bg`
* Hintergrundton für `type="danger"`.
---
* `--callout-title-color`
* Titel-Textfarbe, gemeinsam für alle vier Typen.
---
* `--callout-body-color`
* Text-Farbe des Fließtexts, gemeinsam für alle vier Typen.
{% /table %}

## Beispiel callout.css

Eine `config/styles/callout.css`, die jeden Token auf dieser Seite festlegt, für Hell- und Dunkelmodus. Die Akzentfarben selbst bleiben in beiden Modi gleich; nur die Hintergrundtöne und Textfarben müssen neu abgestimmt werden:

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

## Nächster Schritt

- [Accordions gestalten](/de/customization/advanced/accordions).
