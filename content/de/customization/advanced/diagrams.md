---
title: Diagramme
description: Gestalten Sie die Zeichenfläche, die Lightbox und die Teilnehmerfarben, die von Mordocs Diagrammen verwendet werden.
---

Diese Seite behandelt das Erscheinungsbild der Diagramme. Für die Markdown-Syntax zum Zeichnen eines Diagramms siehe stattdessen [Diagramme](/de/creating-diagrams/overview).

## Die Override-Datei öffnen

```text
config/styles/diagram.css
```

## Zeichenfläche und Steuerelemente

{% table %}
* Token
* Was es steuert
---
* `--diagram-grid-spacing`
* Abstand des gepunkteten Rasters, das hinter jedem Diagramm gezeichnet wird.
---
* `--diagram-grid-dot`
* Das gepunktete Raster-Hintergrundbild selbst. Standardmäßig ein radialer Verlauf unter Verwendung von `--color-border`.
---
* `--diagram-radius`
* Eckenradius der Inline-Diagrammfigur.
---
* `--diagram-overlay-bg`
* Hintergrund hinter der Vollbild-Lightbox.
---
* `--diagram-lightbox-radius`
* Eckenradius des Lightbox-Panels.
---
* `--diagram-button-radius`
* Eckenradius des Schließen-Buttons der Lightbox und der Zoom-Steuerelemente-Pille.
---
* `--diagram-zoom-button-radius`
* Eckenradius der `+`/`−`-Buttons innerhalb der Zoom-Steuerelemente-Pille.
{% /table %}

## Diagramm-Tinte

Diese färben die eigentliche Zeichnung des Diagramms: Beschriftungen, Lifelines, Pfeile und bis zu acht Teilnehmerfarben. Aktuell nutzen nur Sequenzdiagramme sie, aber sie sind gemeinsame Grundbausteine, aus denen auch jeder zukünftige Diagrammtyp schöpfen kann.

{% table %}
* Token
* Was es steuert
---
* `--diagram-label`
* Textfarbe für Beschriftungen. Folgt `--color-fg`, sodass in der Regel keine separate Festlegung nötig ist.
---
* `--diagram-label-bg`
* Hintergrund hinter einer Beschriftung, der das gepunktete Raster lokal auslöscht. Folgt `--color-surface`.
---
* `--diagram-lifeline`
* Farbe der vertikalen Lifeline eines Teilnehmers.
---
* `--diagram-arrow`
* Farbe der Nachrichtenpfeile zwischen Teilnehmern.
---
* `--diagram-activation-1` … `--diagram-activation-8`
* Acht Teilnehmerfarben, zugewiesen in der Reihenfolge, in der Teilnehmer im Diagramm erscheinen.
{% /table %}

## Beispiel diagram.css

Eine `config/styles/diagram.css`, die jeden Token auf dieser Seite festlegt, für Hell- und Dunkelmodus:

```css
:root {
  --diagram-grid-spacing: 20px;
  --diagram-grid-dot: radial-gradient(circle, #e5e5e5 1px, transparent 1px);
  --diagram-radius: 6px;
  --diagram-overlay-bg: rgba(0, 0, 0, 0.82);
  --diagram-lightbox-radius: 8px;
  --diagram-button-radius: 6px;
  --diagram-zoom-button-radius: 4px;

  --diagram-label: #1c1c1c;
  --diagram-label-bg: #fafafa;
  --diagram-lifeline: #757575;
  --diagram-arrow: #52514e;
  --diagram-activation-1: #2563eb;
  --diagram-activation-2: #16a34a;
  --diagram-activation-3: #db2777;
  --diagram-activation-4: #ca8a04;
  --diagram-activation-5: #0d9488;
  --diagram-activation-6: #ea580c;
  --diagram-activation-7: #6d28d9;
  --diagram-activation-8: #dc2626;
}

.dark {
  --diagram-grid-dot: radial-gradient(circle, #2e2e2e 1px, transparent 1px);
  --diagram-label: #ebebeb;
  --diagram-label-bg: #161616;
  --diagram-lifeline: #4f4e46;
  --diagram-arrow: #b0afaa;
  --diagram-activation-1: #60a5fa;
  --diagram-activation-2: #4ade80;
  --diagram-activation-3: #f472b6;
  --diagram-activation-4: #facc15;
  --diagram-activation-5: #2dd4bf;
  --diagram-activation-6: #fb923c;
  --diagram-activation-7: #a78bfa;
  --diagram-activation-8: #f87171;
}
```

## Nächster Schritt

- [Bilder gestalten](/de/customization/advanced/images).
