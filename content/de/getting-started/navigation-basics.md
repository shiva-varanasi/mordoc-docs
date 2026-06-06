---
title: Navigationsgrundlagen
description: Fügen Sie Seiten zur Mordoc-Seitennavigation hinzu, damit Leser sie finden können.
---

In den vorherigen Schritten haben Sie eine Seite unter folgendem Pfad erstellt:

```text
/my-first-page
```

Die Seite existiert, erscheint aber noch nicht in der Seitenleiste. Mordoc hält Seiten und Navigation getrennt, damit Sie wählen können, welche Seiten Leser im Menü sehen.

In diesem Schritt fügen Sie Ihre neue Seite zur Seitenleiste hinzu.

## Die Navigationsdatei öffnen

Öffnen Sie diese Datei:

```text
config/navigation/sidenav.yaml
```

Die Starter-Datei sieht so aus:

```yaml
- label: The Ring
  expanded: true
  children:
    - label: Lore of the Ring
      path: /lore
    - label: Wielding the Ring
      path: /wielding-the-ring
    - label: Safeguards
      path: /safeguards
```

Diese Datei steuert die in der Seitenleiste angezeigten Links.

## Ihre Seite hinzufügen

Fügen Sie Ihre neue Seite unter `children` hinzu:

```yaml
- label: The Ring
  expanded: true
  children:
    - label: Lore of the Ring
      path: /lore
    - label: Wielding the Ring
      path: /wielding-the-ring
    - label: Safeguards
      path: /safeguards
    - label: My First Page
      path: /my-first-page
```

Speichern Sie die Datei.

Wenn Ihr lokaler Server läuft, sollte die Seitenleiste automatisch aktualisiert werden. Sie sollten nun `My First Page` in der Seitenleiste sehen.

## Was label und path bedeuten

Jedes Navigationselement hat ein `label` und einen `path`.

```yaml
- label: My First Page
  path: /my-first-page
```

Das `label` ist das, was Leser in der Seitenleiste sehen.

Der `path` ist die Seitenadresse, die sich öffnet, wenn sie auf das Label klicken.

## Labels einfach halten

Navigations-Labels sollten kurz und klar sein.

Gute Beispiele:

* `Installieren`
* `Konfiguration`
* `Veröffentlichen`

Vermeiden Sie lange Labels, wenn ein kürzeres ausreichend klar ist.

## Weitere Navigationsoptionen

Diese Seite behandelt nur die erste Seitenleistenbearbeitung.

Später wird die Seite [Seitennavigation](/de/configuration/side-navigation) verschachtelte Gruppen und erweiterte Gruppen erklären. Der Konfigurationsabschnitt erklärt auch die obere Navigation, Header-Links und übersetzte Navigations-Labels.

## Nächster Schritt

[Bilder und Dateien hinzufügen](/de/getting-started/images-and-files).
