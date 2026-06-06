---
title: Routen und Links
description: Verstehen Sie, wie Mordoc Inhaltsdateien in URLs umwandelt und wie Sie zwischen Seiten verlinken.
---

Im vorherigen Schritt haben Sie eine Seitendatei erstellt:

```text
content/en/my-first-page.md
```

Mordoc wandelt diese Datei in eine Seite um, die Sie im Browser öffnen können:

```text
/my-first-page
```

Diese Browser-Adresse wird Route genannt.

## Ihre neue Seite öffnen

Wenn Ihr lokaler Server noch läuft, öffnen Sie diese Adresse in Ihrem Browser:

```text
http://localhost:5173/my-first-page
```

Sie sollten die Seite sehen, die Sie erstellt haben.

## Wie Seitenadressen erstellt werden

Mordoc schaut sich den Dateispeicherort innerhalb von `content/en/` an und erstellt die entsprechende Seitenadresse.

Hier sind einige Beispiele:

```text
content/en/index.md           -> /
content/en/my-first-page.md   -> /my-first-page
content/en/guides/install.md  -> /guides/install
content/en/guides/index.md    -> /guides
```

Der Dateiname `index.md` ist besonders. Er wird zur Hauptseite seines Ordners.

Zum Beispiel:

```text
content/en/index.md        -> /
content/en/guides/index.md -> /guides
```

Dieses Muster werden Sie oft beim Organisieren von Seitengruppen verwenden.

## Zu einer anderen Seite verlinken

Wenn Sie von einer Seite zu einer anderen verlinken, verlinken Sie zur Seitenadresse, nicht zum Dateinamen.

Um zum Beispiel zur Seite zu verlinken, die Sie erstellt haben:

```markdown
[Meine erste Seite lesen](/my-first-page)
```

Schreiben Sie den Link nicht so:

```markdown
[Meine erste Seite lesen](./my-first-page.md)
```

Leser verwenden Seitenadressen im Browser. Ihre Links sollten dieselben Adressen verwenden.

## Zur Startseite verlinken

Die Startseite ist:

```text
/
```

Verlinken Sie sie so:

```markdown
[Zur Startseite](/)
```

## Adressen einfach halten

Verwenden Sie Kleinbuchstaben und Bindestriche in Dateinamen.

Gute Beispiele:

```text
getting-started.md
install-guide.md
account-settings.md
```

Vermeiden Sie Leerzeichen und Sonderzeichen in Dateinamen.

## Weitere Link-Optionen

Später wird der Abschnitt [Inhalte schreiben](/de/writing-content/markdown-basics) weitere Link-Beispiele erklären, einschließlich Links zu Überschriften innerhalb einer Seite.

Später wird die Seite [Sprachen](/de/configuration/languages) erklären, wie Seitenadressen funktionieren, wenn Ihre Website mehr als eine Sprache hat.

## Nächster Schritt

[Seiten zur Navigation hinzufügen](/de/getting-started/navigation-basics).
