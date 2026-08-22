---
title: Header
description: Gestalten Sie die eigenen Abstände, die Logogröße und den Hamburger-Button des Headers, unabhängig von dessen Inhalt.
---

Die Header-Area-Box (aus [App Layout](/de/customization/advanced/app-layout)) enthält die Header-Komponente. Header zeichnet innerhalb dieser Box sein eigenes zweizeiliges Grundgerüst:

```text
┌─────────────────────────────────────────────────────────────┐
│ [Logo]           [        Search        ]      [Actions]    │  primary row
├─────────────────────────────────────────────────────────────┤
│  Link   Link   Link                                         │  top navigation row
└─────────────────────────────────────────────────────────────┘
```

* **Primäre Zeile**: ein Logo links, die Suche zentriert und Aktionen (Header-Links, Sprachauswahl, Theme-Umschalter) rechts. Unterhalb von 768px klappen die Suche und die rechten Aktionen hinter einem Hamburger-Button zusammen.
* **Zeile der oberen Navigation**: nur vorhanden, wenn Ihr Projekt `config/navigation/topnav.yaml` anstelle einer einzelnen Seitennavigation verwendet. Siehe [Obere Navigation](/de/customization/advanced/top-navigation) für deren eigene Tokens.

Diese Seite behandelt die eigenen Abstände des Headers sowie Logo/Hamburger-Button. Header-Links, die Sprachauswahl, der Theme-Umschalter und die Suche haben jeweils eine eigene Seite, unten verlinkt.

## Die Override-Datei öffnen

```text
config/styles/header.css
```

## Tokens

{% table %}
* Token
* Was es steuert
---
* `--header-padding`
* Horizontaler Abstand in beiden Zeilen. Standardmäßig `16px`.
---
* `--primary-area-gap`
* Abstand zwischen Logo, Suche und Aktionen in der primären Zeile. Wächst standardmäßig bei breiteren Breakpoints; das Festlegen dieses Wertes überschreibt alle davon auf einen festen Wert.
---
* `--brand-logo-size`
* Höhe des Logo-Bildes.
---
* `--menu-btn-size`
* Breite und Höhe des mobilen Hamburger-/Schließen-Buttons.
---
* `--menu-btn-radius`
* Eckenradius des mobilen Hamburger-/Schließen-Buttons.
---
* `--menu-btn-icon`
* Größe des Hamburger-/Schließen-Icons innerhalb des Buttons.
{% /table %}

```css
:root {
  --brand-logo-size: 32px;
  --menu-btn-radius: 10px;
}
```

## Beispiel header.css

Eine `config/styles/header.css`, die jeden Token auf dieser Seite festlegt. Keiner davon ist eine Farbe, daher gibt es keine separate Dunkelmodus-Variante festzulegen:

```css
:root {
  --header-padding: 20px;
  --primary-area-gap: 16px;
  --brand-logo-size: 32px;
  --menu-btn-size: 40px;
  --menu-btn-radius: 10px;
  --menu-btn-icon: 22px;
}
```

## Nächster Schritt

- [Header-Links gestalten](/de/customization/advanced/header-links).
