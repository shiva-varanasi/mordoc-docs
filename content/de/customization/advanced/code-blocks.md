---
title: Code-Blöcke
description: Gestalten Sie den Rahmen, die Kopfzeile und den Kopier-Button um einen umzäunten Code-Block.
---

Code Block umschließt jeden umzäunten Code-Block in Ihrem Markdown-Inhalt. Siehe [Markdown-Grundlagen](/de/writing-content/markdown-basics). Diese Seite behandelt den Rahmen: seine Kopfzeile, den Rand und den Kopier-Button.

## Die Override-Datei öffnen

```text
config/styles/code-block.css
```

## Tokens

{% table %}
* Token
* Was es steuert
---
* `--cb-bg`
* Hintergrund der Kopfzeile, die den Sprachnamen anzeigt. Standardmäßig `--color-surface`.
---
* `--cb-border`
* Rand um den gesamten Block und unter der Kopfzeile. Standardmäßig `--color-border`.
---
* `--cb-radius`
* Eckenradius des gesamten Blocks.
---
* `--cb-copy-button-radius`
* Eckenradius des Kopier-Buttons.
{% /table %}

## Beispiel code-block.css

Eine `config/styles/code-block.css`, die jeden Token auf dieser Seite festlegt, für Hell- und Dunkelmodus:

```css
:root {
  --cb-bg: #fafafa;
  --cb-border: #e5e5e5;
  --cb-radius: 6px;
  --cb-copy-button-radius: 4px;
}

.dark {
  --cb-bg: #161616;
  --cb-border: #2e2e2e;
}
```

Sie müssen nicht jeden Token wie in diesem Beispiel festlegen. Fügen Sie nur die hinzu, die Sie tatsächlich ändern möchten; jeder ausgelassene Token behält Mordocs Standardwert.

## Nächster Schritt

- [Diagramme gestalten](/de/customization/advanced/diagrams).
