---
title: Schriftfamilie
description: Ersetzen Sie Mordocs Standardschriftart für Fließtext und Code durch Ihre eigenen Schriftdateien.
---

Mordoc rendert Fließtext in `Inter` und Code in einem monospaced Standard-Stack.

Wenn Ihre Marke eine eigene Schriftart hat, können Sie diese in `config/site.json` registrieren, und Mordoc verwendet sie überall, wo diese Rolle vorkommt: Fließtext, Überschriften, Navigation und Schaltflächen für die eine Rolle, Code-Blöcke und Inline-Code für die andere.

## Schritt 1 – Die Schriftdateien hinzufügen

Schriftdateien befinden sich hier:

```text
config/assets/fonts/
```

Fügen Sie eine Datei pro vorhandenem Stil hinzu: eine normale Schriftstärke und optional eine kursive. Mordoc erwartet **variable Schriftarten** (eine einzelne Datei, die einen ganzen Schriftstärkenbereich abdeckt, `100`–`900`), nicht eine Datei pro Schriftstärke.

Unterstützte Dateitypen sind `.woff2`, `.woff` und `.ttf`. `.woff2` ist kleiner und lädt schneller, bevorzugen Sie es daher, wenn Ihr Schriftartenanbieter eine Wahl bietet.

Zum Beispiel:

```text
config/assets/fonts/
├── SpaceGrotesk.woff2
├── SpaceMono.woff2
└── SpaceMono-Italic.woff2
```

## Schritt 2 – Die Schriftart in site.json registrieren

Fügen Sie ein `fonts`-Feld zu `config/site.json` hinzu, mit einem Slot pro Rolle:

```json
{
  "fonts": {
    "body": {
      "family": "Space Grotesk",
      "regular": "SpaceGrotesk.woff2"
    },
    "code": {
      "family": "Space Mono",
      "regular": "SpaceMono.woff2",
      "italic": "SpaceMono-Italic.woff2"
    }
  }
}
```

* `family`: der Name der Schriftart, verwendet, um sie zu registrieren und der Rolle zuzuweisen.
* `regular`: Dateiname der normalen Schriftstärke, aufgelöst relativ zu `config/assets/fonts/`.
* `italic`: Dateiname der kursiven Datei. Optional; lassen Sie das Feld weg, wenn Sie keine haben.

Speichern und aktualisieren. Fließtext und Code werden jetzt beide in ihren neuen Schriftarten dargestellt.

## Die zwei Schriftrollen

`fonts` hat zwei unabhängige Slots:

{% table %}
* Slot
* Verwendet für
---
* `body`
* Fließtext, Überschriften, Navigation und Schaltflächen auf der gesamten Website.
---
* `code`
* Code-Blöcke und Inline-Code.
{% /table %}

Sie können einen Slot ohne den anderen deklarieren. Ein Projekt, das nur eine benutzerdefinierte Überschriften-/Fließtextschrift möchte und mit dem monospaced Standard-Stack für Code zufrieden ist, würde nur `fonts.body` hinzufügen:

```json
{
  "fonts": {
    "body": {
      "family": "Space Grotesk",
      "regular": "SpaceGrotesk.woff2"
    }
  }
}
```

Jeder ausgelassene Slot fällt auf Mordocs Standard für diese Rolle zurück: Inter für `body`, der monospaced Standard-Systemstack für `code`. Nichts geht kaputt, wenn Sie nie ein `fonts`-Feld hinzufügen.

{% callout type="note" title="Nur normal ist in Ordnung" %}
`italic` ist bei beiden Slots optional. Wenn Sie nur `regular` angeben, erzeugt Mordoc die kursive Variante daraus synthetisch, genau wie es ein Browser bei jeder Schriftart ohne eigene kursive Datei tun würde.
{% /callout %}

## Nächster Schritt

- [Erweiterte Anpassung](/de/customization/advanced).
