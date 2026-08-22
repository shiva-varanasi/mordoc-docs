---
title: Abschnitte
description: Gestalten Sie den Standard-Hintergrund für Abschnittsblöcke auf Landing-Pages.
---

Section gruppiert Inhalte auf einer Landing-Page. Siehe [Landing-Pages](/de/writing-content/landing-pages) für die Markdown-Syntax. Es hat einen einzigen website-weiten Token; alles andere (Titel- und Fließtext-Farbe) stammt bereits aus den globalen Tokens in [Design Tokens](/de/customization/advanced/design-tokens).

## Die Override-Datei öffnen

```text
config/styles/section.css
```

## Tokens

{% table %}
* Token
* Was es steuert
---
* `--section-bg`
* Einfarbiger Hintergrund, verwendet, wenn ein Abschnitt kein `background`-Bild hat. Standardmäßig transparent.
{% /table %}

```css
:root {
  --section-bg: #f8fafc;
}
```

## Beispiel section.css

Eine `config/styles/section.css` für Hell- und Dunkelmodus:

```css
:root {
  --section-bg: #f8fafc;
}

.dark {
  --section-bg: #0f172a;
}
```

## Nächster Schritt

- [Schaltflächen gestalten](/de/customization/advanced/buttons).
