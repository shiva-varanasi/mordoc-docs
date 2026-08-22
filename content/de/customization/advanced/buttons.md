---
title: Schaltflächen
description: Gestalten Sie die primäre und sekundäre Schaltflächen-Variante, die auf Landing-Pages und im Header verwendet werden.
---

Button wird überall dort gerendert, wo der `{% button %}`-Tag verwendet wird. Siehe [Landing-Pages](/de/writing-content/landing-pages) für die Markdown-Syntax. Es hat zwei Varianten, `primary` und `secondary`, jede mit eigenen Tokens.

## Die Override-Datei öffnen

```text
config/styles/button.css
```

## Gemeinsame Form

{% table %}
* Token
* Was es steuert
---
* `--button-height`
* Höhe der Schaltfläche, beide Varianten.
---
* `--button-padding`
* Horizontaler Abstand, beide Varianten.
---
* `--button-font-size`
* Schriftgröße, beide Varianten.
---
* `--button-radius`
* Eckenradius, beide Varianten.
---
* `--button-shadow`
* Schlagschatten im Ruhezustand. Standardmäßig `none`; legen Sie ihn für ein Theme fest, dessen Schaltflächenfarbe nah am Hintergrund liegt, damit die Schaltfläche weiterhin als eigene Form erkennbar bleibt.
---
* `--button-shadow-hover`
* Schlagschatten bei Hover.
{% /table %}

## Primäre Variante

{% table %}
* Token
* Was es steuert
---
* `--button-primary-bg`
* Hintergrund. Standardmäßig `--accent`.
---
* `--button-primary-border`
* Randfarbe. Standardmäßig `--accent`.
---
* `--button-primary-fg`
* Textfarbe. Standardmäßig Weiß.
---
* `--button-primary-hover-bg`
* Hintergrund bei Hover.
---
* `--button-primary-hover-border`
* Randfarbe bei Hover.
{% /table %}

## Sekundäre Variante

{% table %}
* Token
* Was es steuert
---
* `--button-secondary-fg`
* Textfarbe. Standardmäßig `--accent`.
---
* `--button-secondary-hover-bg`
* Hintergrund bei Hover.
{% /table %}

{% callout type="note" title="Header-Links nutzen dieselben Tokens" %}
Ein als Schaltfläche konfigurierter Header-Link (siehe [Header-Links](/de/customization/advanced/header-links)) wird über dieselbe Komponente gerendert, nur in einer kleineren, lokal von dieser Datei festgelegten Höhe/Abstand/Schriftgröße. Eine Änderung der Farben hier ändert beide Stellen gleichzeitig.
{% /callout %}

## Beispiel button.css

Eine `config/styles/button.css`, die jeden Token auf dieser Seite festlegt, für Hell- und Dunkelmodus:

```css
:root {
  --button-height: 2.625rem;
  --button-padding: 1.375rem;
  --button-font-size: 0.9375rem;
  --button-radius: 999px;
  --button-shadow: none;
  --button-shadow-hover: none;

  --button-primary-bg: #0d9488;
  --button-primary-border: #0d9488;
  --button-primary-fg: #ffffff;
  --button-primary-hover-bg: #0f766e;
  --button-primary-hover-border: #0f766e;

  --button-secondary-fg: #0d9488;
  --button-secondary-hover-bg: #f0fdfa;
}

.dark {
  --button-primary-bg: #2dd4bf;
  --button-primary-border: #2dd4bf;
  --button-primary-fg: #0f172a;
  --button-primary-hover-bg: #5eead4;
  --button-primary-hover-border: #5eead4;

  --button-secondary-fg: #2dd4bf;
  --button-secondary-hover-bg: #0f2e2b;
}
```

Sie haben jetzt jeden Teil von Mordocs Oberfläche behandelt. Bringen Sie Ihre Website von hier aus live:

## Nächster Schritt

- [Ihre Website bauen](/de/publishing/build-your-site).
