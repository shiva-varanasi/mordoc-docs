---
title: Theme-Umschalter
description: Gestalten Sie den Hell-/Dunkelmodus-Schalter, der im Header angezeigt wird.
---

`config/styles/theme-toggle.css` gestaltet die Schaltfläche, mit der Leser zwischen Hell- und Dunkelmodus wechseln.

## Die Override-Datei öffnen

```text
config/styles/theme-toggle.css
```

## Tokens

{% table %}
* Token
* Was es steuert
---
* `--theme-toggle-size`
* Breite und Höhe der Schaltfläche.
---
* `--theme-toggle-radius`
* Eckenradius der Schaltfläche.
---
* `--theme-toggle-icon-size`
* Größe des Sonne-/Mond-Icons innerhalb der Schaltfläche.
---
* `--theme-toggle-bg`
* Hintergrund der Schaltfläche.
---
* `--theme-toggle-bg-hover`
* Hintergrund der Schaltfläche bei Hover.
---
* `--theme-toggle-border`
* Randfarbe der Schaltfläche.
---
* `--theme-toggle-fg`
* Icon-Farbe.
{% /table %}

## Beispiel theme-toggle.css

Eine `config/styles/theme-toggle.css`, die jeden Token auf dieser Seite festlegt, für Hell- und Dunkelmodus:

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

## Nächster Schritt

- [Die Suche gestalten](/de/customization/advanced/search).
