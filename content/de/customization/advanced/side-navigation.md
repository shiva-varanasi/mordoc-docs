---
title: Seitennavigation
description: Gestalten Sie die Farben und Schriftstärke der Seitennavigation innerhalb der Sidenav-Area-Box.
---

Diese Seite behandelt das **Erscheinungsbild**: `config/styles/sidenav.css`. Um die Navigationselemente selbst hinzuzufügen, zu entfernen oder zu verschachteln, siehe stattdessen [Seitennavigation](/de/configuration/side-navigation) unter Konfiguration.

Die Seitennavigation wird innerhalb der Sidenav-Area-Box aus [App Layout](/de/customization/advanced/app-layout) gerendert, die für Platzierung, Breite und Hintergrund der Box zuständig ist. Diese Datei gestaltet nur die Zeilen darin: Gruppenlabels, Links und den aktiven Zustand.

## Die Override-Datei öffnen

```text
config/styles/sidenav.css
```

## Tokens

{% table %}
* Token
* Was es steuert
---
* `--sidenav-row-radius`
* Eckenradius, gemeinsam für jeden Zeilentyp: Gruppenlabels und Links.
---
* `--sidenav-fg`
* Textfarbe von Links und verlinkten Gruppenlabels.
---
* `--sidenav-fg-muted`
* Farbe des Auf-/Zuklapp-Chevrons.
---
* `--sidenav-group-label-fg`
* Textfarbe eines nicht verlinkten Gruppenlabels (eine Überschrift, die nur auf-/zuklappt, wie „Getting Started").
---
* `--sidenav-hover-bg`
* Hintergrund, der bei Hover für jede Zeile angezeigt wird.
---
* `--sidenav-active-fg`
* Textfarbe des Links der aktuellen Seite.
---
* `--sidenav-active-bg`
* Hintergrund des Links der aktuellen Seite.
---
* `--sidenav-font-weight`
* Schriftstärke von Links und Gruppenlabels.
---
* `--sidenav-active-font-weight`
* Schriftstärke des Links der aktuellen Seite.
{% /table %}

```css
:root {
  --sidenav-active-fg: #0f766e;
  --sidenav-active-bg: #ecfdf5;
}
```

{% callout type="note" title="Form und Größe sind bewusst fest vorgegeben" %}
Zeilenabstand, Zeilenhöhe und Schriftgröße sind nicht als Tokens verfügbar. Mordoc hält diese fest, damit die Seitenleiste über jede Website hinweg konsistent wirkt, statt unabhängig abgestimmt werden zu müssen. Nur Farbe und Schriftstärke sind hier anpassbar.
{% /callout %}

## Beispiel sidenav.css

Eine `config/styles/sidenav.css`, die jeden Token auf dieser Seite festlegt, für Hell- und Dunkelmodus:

```css
:root {
  --sidenav-row-radius: 6px;
  --sidenav-fg: #383838;
  --sidenav-fg-muted: #666666;
  --sidenav-group-label-fg: rgba(56, 56, 56, 0.7);
  --sidenav-hover-bg: #efefef;
  --sidenav-active-fg: #0f766e;
  --sidenav-active-bg: #ecfdf5;
  --sidenav-font-weight: 500;
  --sidenav-active-font-weight: 600;
}

.dark {
  --sidenav-fg: #d4d4d4;
  --sidenav-fg-muted: #9e9e9e;
  --sidenav-group-label-fg: rgba(214, 214, 214, 0.7);
  --sidenav-hover-bg: #1f1f1f;
  --sidenav-active-fg: #2dd4bf;
  --sidenav-active-bg: #0f2e2b;
}
```

## Nächster Schritt

- [Das Inhalts-Layout gestalten](/de/customization/advanced/content-layout).
