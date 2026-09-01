---
title: Accordions
description: Gestalten Sie die einklappbaren Abschnitte, die Sie im Fließtext eines Artikels platzieren.
---

Accordion und Accordions sind Komponenten, die Sie im Fließtext eines Artikels platzieren. Siehe [Accordions](/de/writing-content/accordions) für die Markdown-Syntax. Diese Seite behandelt ihr Erscheinungsbild.

## Die Override-Datei öffnen

```text
config/styles/accordion.css
```

## Tokens

{% table %}
* Token
* Was es steuert
---
* `--accordion-bg`
* Hintergrund von Header und Body. Standardwert `--color-bg`.
---
* `--accordion-border`
* Randfarbe der gesamten Box bei einem eigenständigen Accordion, der Trenner zwischen den Elementen einer Gruppe. Standardwert `--color-border`.
---
* `--accordion-radius`
* Eckenradius eines eigenständigen Accordions und der Gruppenbox, die mehrere umschließt.
---
* `--accordion-shadow`
* Schlagschatten eines eigenständigen Accordions und der Gruppenbox, die mehrere umschließt.
---
* `--accordion-title-color`
* Header-Textfarbe. Standardwert `--color-fg`.
---
* `--accordion-content-color`
* Body-Textfarbe. Standardwert `--color-content-fg`.
---
* `--accordion-chevron-color`
* Farbe des Chevron-Icons zum Auf- und Zuklappen. Standardwert `--color-fg-muted`.
---
* `--accordion-hover-bg`
* Header-Hintergrund beim Hover.
{% /table %}

## Beispiel accordion.css

Eine `config/styles/accordion.css`, die jeden Token auf dieser Seite festlegt, für Hell- und Dunkelmodus:

```css
:root {
  --accordion-bg: #ffffff;
  --accordion-border: #e5e5e5;
  --accordion-radius: 10px;
  --accordion-shadow: 0 1px 3px rgba(0, 0, 0, 0.06), 0 1px 2px rgba(0, 0, 0, 0.04);
  --accordion-title-color: #1c1c1c;
  --accordion-content-color: #3f3f3f;
  --accordion-chevron-color: #6b7280;
  --accordion-hover-bg: #f5f5f5;
}

.dark {
  --accordion-bg: #161616;
  --accordion-border: #2e2e2e;
  --accordion-title-color: #ebebeb;
  --accordion-content-color: #c7c7c7;
  --accordion-chevron-color: #9e9e9e;
  --accordion-hover-bg: #1f1f1f;
}
```

## Nächster Schritt

- [Karten und Karten-Raster gestalten](/de/customization/advanced/cards).
