---
title: Artikelseite
description: Gestalten Sie Breadcrumb, Blockquote und den Inline-Code-Chip einer Artikelseite.
---

Article Page wird innerhalb von Contents Artikelspalte gerendert (siehe [Inhalts-Layout](/de/customization/advanced/content-layout)): der Breadcrumb, Titel, die Beschreibung und der aus Ihrem Markdown gerenderte Fließtext.

Der Großteil des Fließtexts (Überschriften, Absätze, Links, Listen, Tabellen) sieht bereits durch die globalen Tokens in [Design Tokens](/de/customization/advanced/design-tokens) (`--color-fg`, `--color-content-fg`, `--color-border`) richtig aus und benötigt keine eigenen Tokens. Nur der Breadcrumb, Blockquotes und der Inline-Code-Chip haben eigene artikelspezifische Tokens.

## Die Override-Datei öffnen

```text
config/styles/article-page.css
```

## Tokens

{% table %}
* Token
* Was es steuert
---
* `--breadcrumb-link`
* Textfarbe eines Breadcrumb-Segments, das zu einer übergeordneten Seite verlinkt.
---
* `--breadcrumb-link-hover`
* Farbe dieses Segments bei Hover.
---
* `--breadcrumb-current`
* Textfarbe des Breadcrumb-Segments der aktuellen Seite (kein Link).
---
* `--breadcrumb-sep`
* Farbe des `›`-Trennzeichens zwischen Breadcrumb-Segmenten.
---
* `--blockquote-radius`
* Eckenradius eines Markdown-`>`-Blockquotes.
---
* `--inline-code-radius`
* Eckenradius von Inline-`` `code` `` im Fließtext.
{% /table %}

## Beispiel article-page.css

Eine `config/styles/article-page.css`, die jeden Token auf dieser Seite festlegt, für Hell- und Dunkelmodus:

```css
:root {
  --breadcrumb-link: #6b6b6b;
  --breadcrumb-link-hover: #1c1c1c;
  --breadcrumb-current: #111827;
  --breadcrumb-sep: #6b6b6b;
  --blockquote-radius: 6px;
  --inline-code-radius: 4px;
}

.dark {
  --breadcrumb-link: #a0a0a0;
  --breadcrumb-link-hover: #eaeaea;
  --breadcrumb-current: #f3f4f6;
}
```

## Nächster Schritt

- [Das Inhaltsverzeichnis gestalten](/de/customization/advanced/table-of-contents).
