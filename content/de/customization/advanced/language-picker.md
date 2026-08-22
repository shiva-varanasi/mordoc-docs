---
title: Sprachauswahl
description: Gestalten Sie den Sprachumschalter, der im Header mehrsprachiger Websites angezeigt wird.
---

Die Sprachauswahl wird nur gerendert, wenn eine Website mehr als eine Sprache konfiguriert hat. Siehe [Sprachen](/de/configuration/languages). `config/styles/language-picker.css` gestaltet ihren Auslöser-Button und das Dropdown.

## Die Override-Datei öffnen

```text
config/styles/language-picker.css
```

## Tokens

{% table %}
* Token
* Was es steuert
---
* `--lang-height`
* Höhe des Auslöser-Buttons.
---
* `--lang-padding`
* Horizontaler Abstand des Auslöser-Buttons.
---
* `--lang-gap`
* Abstand zwischen dem Globus-Icon und dem Sprachcode im Auslöser.
---
* `--lang-radius`
* Eckenradius des Auslöser-Buttons.
---
* `--lang-font-size`
* Schriftgröße des Auslösers und der Dropdown-Optionen.
---
* `--lang-icon-size`
* Größe des Globus-Icons.
---
* `--lang-fg`
* Textfarbe des Auslösers.
---
* `--lang-fg-hover`
* Textfarbe des Auslösers bei Hover.
---
* `--lang-bg-hover`
* Hintergrund des Auslösers bei Hover.
---
* `--lang-active-color`
* Textfarbe der aktuell ausgewählten Sprache im Dropdown.
---
* `--lang-active-bg`
* Hintergrund der aktuell ausgewählten Sprache im Dropdown.
---
* `--lang-dropdown-radius`
* Eckenradius des Dropdown-Panels.
---
* `--lang-dropdown-shadow`
* Schlagschatten unter dem Dropdown-Panel.
---
* `--lang-option-radius`
* Eckenradius jeder Optionszeile im Dropdown.
{% /table %}

## Beispiel language-picker.css

Eine `config/styles/language-picker.css`, die jeden Token auf dieser Seite festlegt, für Hell- und Dunkelmodus:

```css
:root {
  --lang-height: 36px;
  --lang-padding: 10px;
  --lang-gap: 6px;
  --lang-radius: 999px;
  --lang-font-size: 14px;
  --lang-icon-size: 16px;
  --lang-fg: #383838;
  --lang-fg-hover: #1c1c1c;
  --lang-bg-hover: #f5f5f5;
  --lang-active-color: #0f766e;
  --lang-active-bg: #f0fdfa;
  --lang-dropdown-radius: 8px;
  --lang-dropdown-shadow: 0 4px 6px -1px rgba(0, 0, 0, 0.07), 0 2px 4px -1px rgba(0, 0, 0, 0.04);
  --lang-option-radius: 4px;
}

.dark {
  --lang-fg: #9e9e9e;
  --lang-fg-hover: #ebebeb;
  --lang-bg-hover: #1f1f1f;
  --lang-active-color: #2dd4bf;
  --lang-active-bg: #0f2e2b;
}
```

Sie müssen nicht jeden Token wie in diesem Beispiel festlegen. Fügen Sie nur die hinzu, die Sie tatsächlich ändern möchten; jeder ausgelassene Token behält Mordocs Standardwert.

## Nächster Schritt

- [Den Theme-Umschalter gestalten](/de/customization/advanced/theme-toggle).
