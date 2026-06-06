---
title: Sprachen
description: Verstehen Sie, wie Mordoc Sprachordner und optionale Spracheinstellungen verwendet.
---

Mordoc verwendet Ordner innerhalb von `content/`, um Sprachen zu organisieren.

Das Starter-Projekt hat eine Sprache:

```text
content/
└── en/
```

Das bedeutet, dass die Starter-Website auf Englisch verfasst ist.

## Die Standardsprache verstehen

Die Standardsprache wird in `config/site.json` festgelegt:

```json
{
  "defaultLanguage": "en"
}
```

Da `en` die Standardsprache ist, erhalten Seiten innerhalb von `content/en/` kein Sprachpräfix in ihren Routen.

Zum Beispiel:

```text
content/en/index.md          -> /
content/en/guides/index.md   -> /guides
content/en/guides/install.md -> /guides/install
```

## Einen weiteren Sprachordner hinzufügen

Wenn Sie eine weitere Sprache hinzufügen, erstellen Sie einen weiteren Ordner innerhalb von `content/`.

Zum Beispiel:

```text
content/
├── en/
└── fr/
```

Seiten in anderen Sprachen als der Standardsprache verwenden den Sprachcode als Routen-Präfix.

```text
content/fr/index.md          -> /fr
content/fr/guides/index.md   -> /fr/guides
content/fr/guides/install.md -> /fr/guides/install
```

## Die Seitenstruktur gleich halten

Behalten Sie in jeder Sprache dieselbe Ordner- und Dateistruktur bei:

```text
content/
├── en/
│   └── guides/
│       └── install.md
└── fr/
    └── guides/
        └── install.md
```

Dies ist erforderlich, da die Website eine Navigationsstruktur für alle Sprachen verwendet.

Die Seiten- und obere Navigation verweisen auf Routen wie:

```text
/guides/install
```

Wenn ein Leser die Sprache wechselt, verwendet Mordoc die passende Route in der ausgewählten Sprache.

Zum Beispiel:

```text
content/en/guides/install.md -> /guides/install
content/fr/guides/install.md -> /fr/guides/install
```

## Fehlende Sprachinhalte

Wenn eine Sprache in `config/language.json` aufgeführt ist, aber ihr Inhaltsordner fehlt oder leer ist, kann Mordoc zur Laufzeit auf den Standardsprachen-Inhalt zurückgreifen.

Wenn zum Beispiel `fr` hier aufgeführt ist:

```json
{
  "languages": ["en", "fr"]
}
```

Aber dieser Ordner existiert noch nicht:

```text
content/fr/
```

Kann Mordoc trotzdem den Standardsprachen-Inhalt verwenden.

Dieses Fallback ist hilfreich, während Übersetzungen in Arbeit sind. Übersetzte Inhalte sollten jedoch beim Hinzufügen dieselbe Ordner- und Dateistruktur befolgen.

## Die Sprachliste hinzufügen

Wenn Ihre Website mehr als eine Sprache hat, erstellen Sie:

```text
config/language.json
```

Listen Sie die Sprachcodes auf, die Ihre Website unterstützt:

```json
{
  "languages": ["en", "fr"]
}
```

Der `languages`-Wert muss ein Array von Sprachcodes sein.

Wenn Sie `config/language.json` erstellen, muss die Standardsprache aus `config/site.json` in der Liste enthalten sein.

Wenn zum Beispiel `defaultLanguage` `en` ist, muss `en` in `languages` erscheinen.

Für eine einsprachige Website benötigen Sie `config/language.json` nicht.

## Navigations-Labels übersetzen

Nachdem Sie eine weitere Sprache hinzugefügt haben, möchten Sie möglicherweise auch Navigations-Labels übersetzen.

Das wird durch Dateien in folgendem Verzeichnis gesteuert:

```text
config/navigation/translations/
```

Lesen Sie [Navigationsübersetzungen](/de/configuration/navigation-translations), wenn Sie bereit für diesen Schritt sind.

## Nächster Schritt

[Navigationsübersetzungen konfigurieren](/de/configuration/navigation-translations).
