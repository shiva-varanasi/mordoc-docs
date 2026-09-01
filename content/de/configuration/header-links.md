---
title: Header-Links
description: Fügen Sie kompakte Links zu externen Zielen wie Repositories, API-Referenzen oder Login-Seiten hinzu.
---

Header-Links sind optionale Links, die im Website-Header angezeigt werden.

Sie sind nützlich für Ziele außerhalb der Dokumentationswebsite, die Leser häufig benötigen.

Sie könnten zum Beispiel zu einem Quell-Repository, einer gehosteten API-Referenz, einem Support-Portal oder der Anmeldeseite Ihres Unternehmens verlinken.

## Die Header-Navigationsdatei erstellen

Header-Links befinden sich in dieser optionalen Datei:

```text
config/navigation/headernav.yaml
```

Erstellen Sie die Datei nur, wenn Sie Header-Links benötigen.

## Einen Link hinzufügen

Beginnen Sie mit einer kleinen Liste:

```yaml
- label: GitHub
  path: https://github.com/example/project

- label: API Reference
  path: https://api.example.com

- label: Sign in
  path: https://app.example.com/login
  variant: primary
```

Verwenden Sie `label` für den sichtbaren Text.

Verwenden Sie `path` für die vollständige Website-Adresse.

Verwenden Sie `variant`, wenn ein Link wie eine Schaltfläche aussehen soll. Der Wert kann `link`, `primary` oder `secondary` sein.

## Links sorgfältig auswählen

Header-Links sollten nützlich wirken, nicht überfüllt.

Häufige Optionen sind:

* Ein Quell-Repository
* Eine außerhalb von Mordoc gehostete API-Referenz
* Ein Support-Portal
* Eine Community-Seite
* Eine Anmelde- oder Registrierungsseite

Verwenden Sie für normale Dokumentationsseiten die [Seitennavigation](/de/configuration/side-navigation).

Verwenden Sie für separate Dokumentationsbereiche mit eigenen Seitenleisten die [obere Navigation](/de/configuration/top-navigation).

## Vollständige URLs verwenden

Header-Links zeigen in der Regel auf externe Adressen, verwenden Sie daher die vollständige URL:

```yaml
- label: Support
  path: https://example.com/support
```

## Speichern und den Header überprüfen

Speichern Sie `config/navigation/headernav.yaml`.

Wenn Ihr lokaler Server läuft, überprüfen Sie den Header-Bereich der Website und stellen Sie sicher, dass jeder Link dorthin führt, wo Sie es erwarten.

## Nächster Schritt

[Footer konfigurieren](/de/configuration/footer).
