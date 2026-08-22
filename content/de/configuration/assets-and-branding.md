---
title: Assets und Branding
description: Ersetzen Sie das Website-Logo, das Dark-Logo, das Favicon und das Sharing-Bild.
---

Mordoc verwendet zwei Orte für Bilddateien:

```text
config/assets/
public/
```

Sie haben unterschiedliche Aufgaben. Verwenden Sie `config/assets/` für die Website-Oberfläche, wie Logos. Verwenden Sie `public/` für Bilder und Dateien, die von Ihren Inhaltsseiten verwendet werden.

## Config-Assets verstehen

Website-Branding-Dateien befinden sich in:

```text
config/assets/
```

Das Starter-Projekt enthält:

```text
config/assets/
├── logo.svg
└── logo-dark.svg
```

Diese Dateien werden von der Website-Oberfläche verwendet, nicht von einer bestimmten Markdown-Seite.

## Das Logo ersetzen

Um das Hellmodus-Logo zu ersetzen, ersetzen Sie:

```text
config/assets/logo.svg
```

Behalten Sie den Dateinamen `logo` und verwenden Sie einen unterstützten Bilddateityp.

Zum Beispiel:

```text
config/assets/logo.svg
```

Unterstützte Bilddateitypen sind SVG, PNG, JPG und JPEG.

## Das Dark-Logo ersetzen

Wenn Ihr Logo eine andere Version auf dunklen Hintergründen benötigt, fügen Sie Folgendes hinzu oder ersetzen Sie:

```text
config/assets/logo-dark.svg
```

Das Dark-Logo sollte dem Hellmodus-Logo in Größe und Form so eng wie möglich entsprechen. Das hilft, den Header stabil zu halten, wenn sich das Theme ändert.

## Ein Favicon hinzufügen

Ein Favicon ist das kleine Symbol, das Browser in Tabs und Lesezeichen anzeigen.

Fügen Sie es hier hinzu:

```text
config/assets/favicon.ico
```

Sie können dies überspringen, während Sie Ihre Dokumentation entwerfen. Fügen Sie es vor der Veröffentlichung hinzu, wenn Ihre Website ein gebrandetes Browser-Symbol verwenden soll.

## Public für Inhaltsdateien verwenden

Legen Sie Screenshots, Diagramme, Downloads oder andere Inhaltsdateien nicht in `config/assets/` ab.

Diese Dateien gehören in `public/`. Lesen Sie [Bilder und Dateien](/de/getting-started/images-and-files) für die vollständige Anleitung.

## Ein Sharing-Bild festlegen

Das Starter-Projekt enthält ein Sharing-Bild:

```text
public/images/ring-og.svg
```

Sie können in `config/site.json` auf ein Sharing-Bild verweisen:

```json
{
  "metadata": {
    "ogImage": "/images/ring-og.svg"
  }
}
```

Da sich die Datei in `public/` befindet, beginnt der Pfad mit `/` und enthält nicht `public`.

## Nächster Schritt

[Das Erscheinungsbild Ihrer Website anpassen](/de/customization/basic).