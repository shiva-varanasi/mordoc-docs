---
title: Obere Navigation
description: Teilen Sie eine größere Mordoc-Website in wichtige Dokumentationsbereiche auf, jeder mit seiner eigenen Seitenleiste.
---

Die obere Navigation ist für größere Dokumentationswebsites gedacht, die mehr als einen Hauptbereich benötigen.

Ein Unternehmen könnte zum Beispiel eine Dokumentationswebsite mit separaten Bereichen für verschiedene Produkte, Teams oder Handbücher haben. Jeder Bereich kann seine eigene Seitennavigations-Struktur haben.

Wenn Ihre Dokumentation eine einfache Seitenleiste hat, benötigen Sie keine obere Navigation. Verwenden Sie stattdessen die [Seitennavigation](/de/configuration/side-navigation).

## Die Datei für die obere Navigation erstellen

Die obere Navigation ist optional. Wenn Sie sie verwenden möchten, erstellen Sie diese Datei:

```text
config/navigation/topnav.yaml
```

Jedes Element der oberen Navigation verweist auf einen Dokumentationsbereich und benennt die Seitennavigations-Datei für diesen Bereich:

```yaml
- label: Field Manual
  path: /field-manual
  sidenav: field-manual.yaml

- label: Ship Systems
  path: /ship-systems
  sidenav: ship-systems.yaml
```

Jedes Element benötigt:

* `label` für den Text, den Leser in der oberen Navigation sehen
* `path` für die Seite, die geöffnet wird, wenn Leser auf das Element der oberen Navigation klicken
* `sidenav` für die Seitennavigations-Datei, die zu diesem Bereich gehört

Der `path` sollte in der Regel die Startseite dieses Dokumentationsbereichs sein. Es kann eine Übersichtsseite im passenden Seitennavigations-Baum oder eine Landing-Page sein, die diesen Bereich vorstellt.

## Die Seitennavigations-Dateien hinzufügen

Die von `sidenav` benannten Dateien befinden sich im selben Navigationsordner:

```text
config/navigation/
├── topnav.yaml
├── field-manual.yaml
└── ship-systems.yaml
```

Wenn Sie `topnav.yaml` verwenden, ersetzen diese benannten Dateien das einzelne website-weite `sidenav.yaml`-Muster.

Jede benannte Seitennavigations-Datei verwendet dieselbe Struktur wie `sidenav.yaml`.

Zum Beispiel könnte `config/navigation/field-manual.yaml` Folgendes enthalten:

```yaml
- label: Field Manual
  expanded: true
  children:
    - label: Overview
      path: /field-manual
    - label: Safety Rules
      path: /field-manual/safety-rules
    - label: Emergency Procedures
      path: /field-manual/emergency-procedures
```

Und `config/navigation/ship-systems.yaml` könnte Folgendes enthalten:

```yaml
- label: Ship Systems
  expanded: true
  children:
    - label: Overview
      path: /ship-systems
    - label: Engines
      path: /ship-systems/engines
    - label: Navigation Console
      path: /ship-systems/navigation-console
```

## Wie Mordoc die Seitenleiste auswählt

Wenn `topnav.yaml` vorhanden ist, verwendet Mordoc die Elemente der oberen Navigation, um zu entscheiden, welche Seitenleiste angezeigt werden soll.

Wenn sich der Leser auf einer Seite unter dieser Route befindet:

```text
/field-manual
```

Verwendet Mordoc:

```text
config/navigation/field-manual.yaml
```

Wenn sich der Leser auf einer Seite unter dieser Route befindet:

```text
/ship-systems
```

Verwendet Mordoc:

```text
config/navigation/ship-systems.yaml
```

Das bedeutet, dass jeder wichtige Dokumentationsbereich eine fokussierte Seitenleiste haben kann.

## Routen-Pfade verwenden

Der `path` in `topnav.yaml` sollte eine Route in Ihrer Website sein:

```yaml
- label: Field Manual
  path: /field-manual
  sidenav: field-manual.yaml
```

Verwenden Sie keinen Markdown-Dateipfad:

```yaml
- label: Field Manual
  path: /content/en/field-manual/index.md
  sidenav: field-manual.yaml
```

## Die Liste kurz halten

Die obere Navigation funktioniert am besten, wenn sie einige wenige wichtige Dokumentationsbereiche enthält.

Gute Labels für die obere Navigation könnten sein:

* `Feldhandbuch`
* `Schiffssysteme`
* `Crew-Handbuch`

Platzieren Sie nicht jede Seite in der oberen Navigation. Fügen Sie Seiten in die Seitennavigations-Datei des Bereichs ein, zu dem sie gehören.

Die verfügbaren Seitennavigations-Felder finden Sie unter [Seitennavigation](/de/configuration/side-navigation).

## Speichern und den Header überprüfen

Speichern Sie `config/navigation/topnav.yaml`.

Wenn Ihr lokaler Server läuft, überprüfen Sie den oberen Bereich der Website. Sie sollten Ihre Labels der oberen Navigation sehen.

Klicken Sie auf jedes Element der oberen Navigation und stellen Sie sicher, dass sich die Seitenleiste zum passenden Bereich ändert.

## Nächster Schritt

[Header-Links konfigurieren](/de/configuration/header-links).
