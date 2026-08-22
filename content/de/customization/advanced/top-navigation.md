---
title: Obere Navigation
description: Gestalten Sie die zweite Header-Zeile, die angezeigt wird, wenn ein Projekt bereichsweise obere Navigation verwendet.
---

Diese Seite behandelt das **Erscheinungsbild**: `config/styles/topnav.css`. Um die obere Navigation selbst einzurichten, die bereichsweisen Abschnitte und welche Seitennavigation jeweils verlinkt wird, siehe stattdessen [Obere Navigation](/de/configuration/top-navigation) unter Konfiguration.

Wenn ein Projekt `config/navigation/topnav.yaml` verwendet, rendert Header eine zweite Zeile unterhalb der primären. Siehe [Header](/de/customization/advanced/header) dafür, wo diese Zeile sitzt. Jeder Link füllt die gesamte Höhe der Zeile aus, mit einem unteren Rand, der den aktiven markiert.

## Die Override-Datei öffnen

```text
config/styles/topnav.css
```

## Tokens

{% table %}
* Token
* Was es steuert
---
* `--topnav-link-padding`
* Horizontaler Abstand jedes Links.
---
* `--topnav-link-font-size`
* Schriftgröße jedes Links.
---
* `--topnav-active-border-width`
* Dicke des unteren Rands, der den aktiven Link markiert.
---
* `--topnav-active-border-color`
* Farbe dieses Rands. Standardmäßig `--accent-emphasis`.
{% /table %}

## Beispiel topnav.css

Eine `config/styles/topnav.css`, die jeden Token auf dieser Seite festlegt, für Hell- und Dunkelmodus:

```css
:root {
  --topnav-link-padding: 0.75rem;
  --topnav-link-font-size: 0.875rem;
  --topnav-active-border-width: 3px;
  --topnav-active-border-color: #0f766e;
}

.dark {
  --topnav-active-border-color: #2dd4bf;
}
```

## Nächster Schritt

- [Die Sprachauswahl gestalten](/de/customization/advanced/language-picker).
