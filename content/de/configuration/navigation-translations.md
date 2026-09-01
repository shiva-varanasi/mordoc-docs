---
title: Navigationsübersetzungen
description: Übersetzen Sie Navigations-Labels für mehrsprachige Mordoc-Websites.
---

Navigationsübersetzungen werden nur benötigt, wenn Ihre Website mehr als eine Sprache hat.

Wenn Ihre Website nur `content/en/` verwendet, können Sie diese Seite vorerst überspringen und später zurückkehren.

## Was übersetzt wird

Ihre Navigationsdateien definieren die Struktur der Navigation:

```text
config/navigation/sidenav.yaml
config/navigation/topnav.yaml
config/navigation/headernav.yaml
```

Übersetzungsdateien ermöglichen es Ihnen, die sichtbaren Labels für eine andere Sprache zu ändern, ohne die gesamte Navigationsstruktur von Grund auf neu aufzubauen.

## Einen Übersetzungsordner erstellen

Navigationsübersetzungsdateien befinden sich hier:

```text
config/navigation/translations/
```

Erstellen Sie eine YAML-Datei für jede übersetzte Sprache.

Zum Beispiel wäre eine französische Übersetzungsdatei:

```text
config/navigation/translations/fr.yaml
```

## Übersetzte Labels hinzufügen

Verwenden Sie die originalen Labels als Schlüssel und geben Sie die übersetzten Labels als Werte an:

```yaml
Getting Started: Premiers pas
Writing Content: Rediger du contenu
Configuration: Configuration
```

Wenn Mordoc die französische Version der Website anzeigt, kann es diese übersetzten Labels in der Navigation verwenden.

## Labels abgleichen

Die Schlüssel in der Übersetzungsdatei sollten mit den Labels übereinstimmen, die in Ihren Navigationsdateien verwendet werden.

Wenn `sidenav.yaml` zum Beispiel Folgendes enthält:

```yaml
- label: Getting Started
  children:
    - label: Create a Project
      path: /getting-started/create-project
```

Dann kann die Übersetzungsdatei Folgendes enthalten:

```yaml
Getting Started: Premiers pas
Create a Project: Creer un projet
```

Wenn ein Label in der Übersetzungsdatei fehlt, kann Mordoc trotzdem das ursprüngliche Label anzeigen.

## Footer-Zeilen übersetzen

Wenn Sie einen [Footer](/de/configuration/footer) konfiguriert haben, werden seine Zeilen in derselben Datei übersetzt, im gleichen Schlüssel-Wert-Format. Verwenden Sie als Schlüssel die exakte Zeile aus `footer.yaml`, einschließlich jeder `[text](url)`-Link-Syntax:

```yaml
"Powered by [Mordoc](https://mordoc.dev)": "Bereitgestellt von [Mordoc](https://mordoc.dev)"
"[Privacy policy](/privacy)": "[Datenschutzrichtlinie](/privacy)"
```

Setzen Sie beide Seiten in Anführungszeichen, wenn die Zeile einen Link enthält. Der Grund ist derselbe wie bei `footer.yaml` selbst: Eine eckige Klammer `[` am Zeilenanfang wird ohne Anführungszeichen als YAML-Liste gelesen.

Anders als bei Sidenav- und Topnav-Pfaden, die Mordoc automatisch mit dem Sprachcode versieht, ist der Pfad einer Footer-Zeile Teil der übersetzten Zeichenkette selbst. Versehen Sie ihn bei einem internen Link von Hand mit dem Präfix:

```yaml
"[Privacy policy](/privacy)": "[Politique de confidentialité](/fr/privacy)"
```

## Zuerst mit Sprachen beginnen

Navigationsübersetzungen ergeben am meisten Sinn, nachdem Ihre Website mehr als einen Sprachordner hat, zum Beispiel:

```text
content/
├── en/
└── fr/
```

Wenn Sie das noch nicht getan haben, beginnen Sie mit [Sprachen](/de/configuration/languages).

## Nächster Schritt

[Variablen konfigurieren](/de/configuration/variables).
