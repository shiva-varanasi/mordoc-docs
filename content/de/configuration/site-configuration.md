---
title: Website-Konfiguration
description: Legen Sie den grundlegenden Namen, die Beschreibung, die Sprache und die öffentliche URL für Ihre Mordoc-Website fest.
---

Ihre Mordoc-Website hat eine zentrale Einstellungsdatei:

```text
config/site.json
```

Diese Datei teilt Mordoc grundlegende Informationen über Ihre Dokumentationswebsite mit. Sie müssen nicht alle Einstellungen auf einmal ändern. Beginnen Sie mit den Feldern, die Leser und Suchmaschinen zuerst sehen werden.

## site.json öffnen

Im Starter-Projekt sieht `config/site.json` so aus:

```json
{
  "name": "The Ring of Power",
  "description": "A field guide for keepers, scholars, and reluctant bearers of the One Ring.",
  "baseUrl": "https://ring-of-power.example.com",
  "defaultLanguage": "en"
}
```

Die Werte sind Teil des Starter-Beispiels. Sie werden sie durch Details für Ihre eigene Dokumentation ersetzen.

## Den Website-Namen ändern

Das `name`-Feld ist der Name Ihrer Dokumentationswebsite.

```json
{
  "name": "Acme Docs"
}
```

Wählen Sie einen kurzen Namen, den Leser erkennen werden. Dies ist in der Regel Ihr Produktname, Projektname oder der Name Ihrer Team-Dokumentation.

## Die Beschreibung ändern

Das `description`-Feld ist eine kurze Zusammenfassung der Website.

```json
{
  "description": "Guides and reference material for Acme users."
}
```

Halten Sie es sachlich und direkt. Ein Satz ist ausreichend.

Diese Beschreibung kann in Seiten-Metadaten und Link-Vorschauen erscheinen, abhängig von der Seite und den Website-Einstellungen.

## Die öffentliche URL festlegen

Das `baseUrl`-Feld ist die öffentliche Adresse, unter der die Website erreichbar sein wird.

```json
{
  "baseUrl": "https://docs.example.com"
}
```

Verwenden Sie die endgültige Website-Adresse, wenn Sie sie kennen.

Wenn Sie noch lokal arbeiten, können Sie den Starter-Wert vorerst belassen und vor der Veröffentlichung zurückkehren.

Verwenden Sie nicht Ihre lokale Vorschau-Adresse, wie `http://localhost:5173`, als endgültige `baseUrl`.

## Die Standardsprache beibehalten

Das `defaultLanguage`-Feld teilt Mordoc mit, welcher Sprachordner der Hauptordner ist.

```json
{
  "defaultLanguage": "en"
}
```

Im Starter-Projekt befinden sich Ihre Seiten in:

```text
content/en/
```

Deshalb ist die Standardsprache `en`.

Sie müssen dies nicht ändern, es sei denn, Sie erstellen eine Website, deren Hauptsprache nicht Englisch ist.

## Die Datei speichern

Speichern Sie die Datei, nachdem Sie `config/site.json` geändert haben.

Wenn Ihr lokaler Server läuft, aktualisieren Sie den Browser, falls Sie die Änderung nicht sofort sehen.

## Metadaten für SEO und Teilen

`config/site.json` kann auch website-weite Metadaten enthalten:

```json
{
  "metadata": {
    "ogImage": "/images/ring-og.svg",
    "ogType": "website",
    "twitterCard": "summary_large_image",
    "twitterSite": "@example"
  }
}
```

Diese Einstellungen helfen Suchmaschinen und sozialen Netzwerken, Ihre Dokumentationswebsite zu verstehen.

Sie sind besonders wichtig für Unternehmensdokumentation, bei der Leser Seiten über Suchergebnisse, geteilte Links, Chat-Vorschauen oder soziale Beiträge finden können.

Beginnen Sie mit `ogImage`. Es verweist auf ein Bild in `public/`, das erscheinen kann, wenn jemand Ihren Website-Link teilt.

Zum Beispiel verweist dieser Wert:

```json
{
  "metadata": {
    "ogImage": "/images/ring-og.svg"
  }
}
```

Auf diese Datei:

```text
public/images/ring-og.svg
```

Die anderen Metadaten-Felder steuern die Art der Vorschau, die externe Dienste anzeigen können.

Eine spätere Seite zu [SEO und Suche](/de/publishing/seo-and-search) erklärt, wie diese Einstellungen mit Seitenbeschreibungen, generierten Suchindizes, `sitemap.xml` und `robots.txt` zusammenwirken.

## Nächster Schritt

[Seitennavigation konfigurieren](/de/configuration/side-navigation).
