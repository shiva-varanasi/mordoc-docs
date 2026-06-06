---
title: Seitennavigation
description: Konfigurieren Sie die Seitenleisten-Links, die Lesern helfen, durch Ihre Dokumentation zu navigieren.
---

Die Seitennavigation ist die Liste der Links, die neben normalen Dokumentationsseiten angezeigt wird.

Sie haben sie bereits unter [Navigationsgrundlagen](/de/getting-started/navigation-basics) verwendet. Diese Seite geht einen Schritt tiefer und zeigt, wie Sie die Seitenleiste organisieren können, wenn Ihre Dokumentation wächst.

## Die Seitennavigations-Datei öffnen

Die Seitennavigation befindet sich hier:

```text
config/navigation/sidenav.yaml
```

Das Starter-Projekt verwendet ein kleines Beispiel:

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

Diese Datei ist in YAML geschrieben. Abstände sind wichtig, also halten Sie die Einrückung konsistent.

## Einen einfachen Link hinzufügen

Ein Seitenleisten-Link benötigt ein `label` und einen `path`:

```yaml
- label: Installation
  path: /installation
```

Das `label` ist das, was Leser sehen.

Der `path` ist die Route, die der Link öffnet. Verwenden Sie die Browser-Route, nicht den `.md`-Dateipfad.

## Verwandte Links gruppieren

Die meisten Dokumentationswebsites verwenden Gruppen:

```yaml
- label: Getting Started
  children:
    - label: Installation
      path: /getting-started/installation
    - label: First Project
      path: /getting-started/first-project
```

Das Gruppen-Label hilft Lesern zu verstehen, was die Links gemeinsam haben.

Verwenden Sie Gruppen, wenn Sie mehrere Seiten haben, die zusammengehören.

## Das Gruppen-Label verlinken

Eine Gruppe kann auch zu einer Seite verlinken.

Dies ist nützlich, wenn die Gruppe eine Übersichtsseite und mehrere Detailseiten hat:

```yaml
- label: Getting Started
  path: /getting-started
  children:
    - label: Installation
      path: /getting-started/installation
    - label: First Project
      path: /getting-started/first-project
```

In diesem Beispiel öffnet das Klicken auf `Getting Started` den Pfad `/getting-started`.

Die untergeordneten Links erscheinen weiterhin unter der Gruppe.

## Eine Gruppe standardmäßig öffnen

Fügen Sie `expanded: true` hinzu, wenn eine Gruppe standardmäßig geöffnet sein soll:

```yaml
- label: Getting Started
  expanded: true
  children:
    - label: Installation
      path: /getting-started/installation
    - label: First Project
      path: /getting-started/first-project
```

Dies ist hilfreich für den ersten Abschnitt, den Leser wahrscheinlich verwenden werden, oder wenn Sie nicht viele Seiten haben und alle Gruppen standardmäßig erweitert sein sollen.

## Labels kurz halten

Verwenden Sie Labels, die auf einen Blick klar sind:

```yaml
- label: Site Configuration
  path: /configuration/site-configuration
```

Vermeiden Sie Labels, die versuchen, die gesamte Seite zu erklären:

```yaml
- label: How to Configure the Main Site Settings
  path: /configuration/site-configuration
```

Der Seitentitel kann länger sein. Das Seitenleisten-Label sollte leicht zu überfliegen bleiben.

## Links mit echten Seiten abgleichen

Wenn Sie diese Datei erstellen:

```text
content/en/configuration/site-configuration.md
```

Verwenden Sie diese Route in der Navigation:

```yaml
- label: Site Configuration
  path: /configuration/site-configuration
```

Verlinken Sie nicht zur Markdown-Datei:

```yaml
- label: Site Configuration
  path: /configuration/site-configuration.md
```

Leser verwenden Routen, also sollte die Navigation auch Routen verwenden.

## Speichern und die Seitenleiste überprüfen

Speichern Sie `config/navigation/sidenav.yaml`.

Wenn Ihr lokaler Server läuft, sollte die Seitenleiste automatisch aktualisiert werden. Klicken Sie jeden neuen Link einmal an, um sicherzustellen, dass er die erwartete Seite öffnet.

## Nächster Schritt

[Obere Navigation konfigurieren](/de/configuration/top-navigation).
