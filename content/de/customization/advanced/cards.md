---
title: Karten und Karten-Raster
description: Gestalten Sie die Karten, die Sie in Rastern auf Landing- und Übersichtsseiten anordnen.
---

Karten sind eine der Komponenten, die Sie im Fließtext eines Artikels platzieren. Siehe [Karten und Karten-Raster](/de/writing-content/cards-and-card-grids) für die Markdown-Syntax. Diese Seite behandelt das Erscheinungsbild der Karten.

## Die Override-Datei öffnen

```text
config/styles/card.css
```

## Tokens

{% table %}
* Token
* Was es steuert
---
* `--card-bg`
* Kartenhintergrund. Standardmäßig `--color-bg`.
---
* `--card-border`
* Kartenrand. Standardmäßig `--color-border`.
---
* `--card-border-hover`
* Randfarbe bei Hover, für eine Karte, die irgendwohin verlinkt. Standardmäßig `--accent`.
---
* `--card-radius`
* Eckenradius der gesamten Karte.
---
* `--card-shadow`
* Schlagschatten im Ruhezustand.
---
* `--card-shadow-hover`
* Schlagschatten bei Hover, für eine verlinkte Karte.
---
* `--card-title-color`
* Titel-Textfarbe. Standardmäßig `--color-fg`.
---
* `--card-desc-color`
* Beschreibungs-Textfarbe. Standardmäßig `--color-fg-muted`.
---
* `--card-tag-bg`
* Hintergrund des kleinen Tag-Abzeichens.
---
* `--card-tag-color`
* Textfarbe des Tag-Abzeichens.
---
* `--card-tag-radius`
* Eckenradius des Tag-Abzeichens.
---
* `--card-arrow-color`
* Farbe des nachgestellten Pfeils bei einer verlinkten Karte, vor Hover.
{% /table %}

```css
:root {
  --card-radius: 14px;
  --card-border-hover: #0d9488;
}
```

Die meisten davon greifen standardmäßig bereits auf einen globalen Token zurück (`--color-bg`, `--accent` und ähnliche), sodass eine Änderung der [Design Tokens](/de/customization/advanced/design-tokens) auch Karten verschiebt, sofern Sie sie hier nicht gezielt überschreiben.

## Beispiel card.css

Eine `config/styles/card.css`, die jeden Token auf dieser Seite festlegt, für Hell- und Dunkelmodus:

```css
:root {
  --card-bg: #ffffff;
  --card-border: #e5e5e5;
  --card-border-hover: #0d9488;
  --card-radius: 14px;
  --card-shadow: 0 1px 3px rgba(0, 0, 0, 0.06), 0 1px 2px rgba(0, 0, 0, 0.04);
  --card-shadow-hover: 0 4px 6px -1px rgba(0, 0, 0, 0.07), 0 2px 4px -1px rgba(0, 0, 0, 0.04);
  --card-title-color: #1c1c1c;
  --card-desc-color: #6b7280;
  --card-tag-bg: #f0fdfa;
  --card-tag-color: #0f766e;
  --card-tag-radius: 4px;
  --card-arrow-color: #6b7280;
}

.dark {
  --card-bg: #161616;
  --card-border: #2e2e2e;
  --card-border-hover: #2dd4bf;
  --card-title-color: #ebebeb;
  --card-desc-color: #9e9e9e;
  --card-tag-bg: #0f2e2b;
  --card-tag-color: #2dd4bf;
  --card-arrow-color: #9e9e9e;
}
```

## Nächster Schritt

- [Code-Blöcke gestalten](/de/customization/advanced/code-blocks).
