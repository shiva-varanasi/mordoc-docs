---
title: Inhalts-Layout
description: Gestalten Sie das eigene Layoutgerüst des Inhaltsbereichs, sowohl das Raster aus Artikel, Inhaltsverzeichnis und Fußzeile als auch das vollbreite Landing-Layout.
---

Content wird innerhalb der Content-Area-Box aus [App Layout](/de/customization/advanced/app-layout) gerendert. Es besitzt eine weitere Layout-Ebene: welches von zwei Gerüsten eine Seite verwendet, und wo das Inhaltsverzeichnis und die Fußzeile darin sitzen.

**Artikelseiten** verwenden ein zweispaltiges Raster, wobei die Fußzeile nur unter der Artikelspalte verläuft:

```text
┌───────────────────────────────────┬──────────────┐
│                                   │              │
│           Article                 │     TOC      │
│                                   │              │
├───────────────────────────────────┤              │
│              Footer               │              │
└───────────────────────────────────┴──────────────┘
```

**Landing-Pages** (`layout: landing` im Frontmatter) verwenden stattdessen die volle Breite, ohne TOC-Spalte:

```text
┌──────────────────────────────────────────────────────┐
│                                                      │
│                   Hero / Sections                    │
│                                                      │
├──────────────────────────────────────────────────────┤
│                        Footer                        │
└──────────────────────────────────────────────────────┘
```

Die TOC-Spalte verschwindet auf Artikelseiten außerdem unterhalb des `1280px`-Breakpoints, sodass nur der Artikel und die Fußzeile in voller Breite gestapelt bleiben.

## Die Override-Datei öffnen

```text
config/styles/content.css
```

## Tokens

{% table %}
* Token
* Was es steuert
---
* `--toc-width`
* Breite der TOC-Spalte auf Artikelseiten. Standardmäßig `16rem`.
---
* `--article-max-width`
* Maximale Breite der Artikel-Lesespalte. Wird auch von der 404-Seite und dem Lade-Skeleton verwendet, sodass sie immer mit der Breite des echten Artikels übereinstimmen.
{% /table %}

```css
:root {
  --article-max-width: 48rem;
}
```

{% callout type="note" title="404 und Lade-Skeleton haben noch keine eigenen" %}
Die Nicht-gefunden-Seite und der schimmernde Lade-Platzhalter, der beim Laden einer Seite angezeigt wird, verwenden beide `--article-max-width` von oben sowie die globalen Farb-Tokens aus [Design Tokens](/de/customization/advanced/design-tokens) wieder. Sie haben keine eigenen komponentenspezifischen Tokens zum Überschreiben.
{% /callout %}

## Beispiel content.css

Eine `config/styles/content.css`, die jeden Token auf dieser Seite festlegt. Keiner davon ist eine Farbe, daher gibt es keine separate Dunkelmodus-Variante festzulegen:

```css
:root {
  --toc-width: 18rem;
  --article-max-width: 48rem;
}
```

## Nächster Schritt

- [Die Artikelseite gestalten](/de/customization/advanced/article-page).
