---
title: Header-Links
description: Gestalten Sie die im Header angezeigten benutzerdefinierten Links, als einfache Links oder Schaltflächen.
---

Diese Seite behandelt das **Erscheinungsbild**: `config/styles/header-links.css`. Um die Links selbst hinzuzufügen, zu entfernen oder umzuordnen, siehe stattdessen [Header-Links](/de/configuration/header-links) unter Konfiguration.

Header-Links werden auf der rechten Seite der primären Header-Zeile gerendert: als einfache unterstrichene Links auf dem Desktop, oder unterhalb von 768px zu einem einzelnen Overflow-Menü-Button zusammengeklappt.

## Die Override-Datei öffnen

```text
config/styles/header-links.css
```

## Tokens

{% table %}
* Token
* Was es steuert
---
* `--header-links-link-color`
* Textfarbe eines Header-Links im einfachen Link-Stil.
---
* `--header-links-link-color-hover`
* Textfarbe bei Hover.
---
* `--header-links-link-padding`
* Horizontaler Abstand um einen Eintrag im einfachen Link-Stil.
---
* `--header-links-link-font-size`
* Schriftgröße eines Eintrags im einfachen Link-Stil.
---
* `--header-links-link-radius`
* Eckenradius eines Eintrags im einfachen Link-Stil (sichtbar an seinem Fokusring).
---
* `--header-links-button-height`
* Höhe eines Header-Links in der Schaltflächen-Variante.
---
* `--header-links-button-padding`
* Horizontaler Abstand eines Header-Links in der Schaltflächen-Variante.
---
* `--header-links-button-font-size`
* Schriftgröße eines Header-Links in der Schaltflächen-Variante.
---
* `--header-links-menu-btn-size`
* Breite und Höhe des mobilen Overflow-Menü-Buttons (der „⋯"-Auslöser).
---
* `--header-links-menu-btn-radius`
* Eckenradius des mobilen Overflow-Menü-Buttons.
---
* `--header-links-dropdown-radius`
* Eckenradius des mobilen Overflow-Dropdown-Panels.
---
* `--header-links-dropdown-item-radius`
* Eckenradius jeder Zeile innerhalb des mobilen Overflow-Dropdowns.
---
* `--header-links-dropdown-item-padding`
* Abstand jeder Zeile innerhalb des mobilen Overflow-Dropdowns.
---
* `--header-links-dropdown-item-font-size`
* Schriftgröße jeder Zeile innerhalb des mobilen Overflow-Dropdowns.
{% /table %}

{% callout type="note" title="Header-Links in der Schaltflächen-Variante nutzen die Tokens von Button" %}
Ein als Schaltfläche konfigurierter Header-Link hat hier keine eigenen Hintergrund-/Rand-Tokens. Er wird mit denselben Tokens wie die [Schaltflächen](/de/customization/advanced/buttons)-Komponente gerendert, nur in der oben festgelegten kompakten Höhe, dem Abstand und der Schriftgröße. Ändern Sie seine Farbe, indem Sie `--button-primary-bg` und verwandte Tokens auf der Seite Schaltflächen überschreiben.
{% /callout %}

## Beispiel header-links.css

Eine `config/styles/header-links.css`, die jeden Token auf dieser Seite festlegt, für Hell- und Dunkelmodus:

```css
:root {
  --header-links-link-color: #0f766e;
  --header-links-link-color-hover: #115e59;
  --header-links-link-padding: 0.25rem;
  --header-links-link-font-size: 0.875rem;
  --header-links-link-radius: 4px;
  --header-links-button-height: 2rem;
  --header-links-button-padding: 0.875rem;
  --header-links-button-font-size: 0.875rem;
  --header-links-menu-btn-size: 40px;
  --header-links-menu-btn-radius: 8px;
  --header-links-dropdown-radius: 8px;
  --header-links-dropdown-item-radius: 6px;
  --header-links-dropdown-item-padding: 0.5rem 0.75rem;
  --header-links-dropdown-item-font-size: 0.875rem;
}

.dark {
  --header-links-link-color: #2dd4bf;
  --header-links-link-color-hover: #5eead4;
}
```

## Nächster Schritt

- [Die obere Navigation gestalten](/de/customization/advanced/top-navigation).
