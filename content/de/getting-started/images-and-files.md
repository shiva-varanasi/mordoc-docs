---
title: Bilder und Dateien
description: Erfahren Sie, wo Sie Logos, Screenshots, Downloads und andere statische Dateien ablegen.
---

Ihre Dokumentation wird häufig Bilder, Screenshots, Diagramme oder herunterladbare Dateien benötigen.

Für Inhaltsdateien gilt eine einfache Hauptregel: Legen Sie sie in `public/` ab und referenzieren Sie sie mit einem Pfad, der mit `/` beginnt.

## Einen Bildordner hinzufügen

Erstellen Sie innerhalb Ihres Projekts einen `images`-Ordner in `public/`:

```text
public/
└── images/
```

Wenn der Ordner bereits existiert, können Sie ihn verwenden.

## Eine Bilddatei hinzufügen

Kopieren Sie ein Bild in diesen Ordner.

Zum Beispiel:

```text
public/images/my-image.png
```

Die Datei kann ein Screenshot, ein Diagramm, eine Illustration oder jedes beliebige Bild sein, das Sie auf einer Seite anzeigen möchten.

## Das Bild auf einer Seite anzeigen

Öffnen Sie die Seite, die Sie zuvor erstellt haben:

```text
content/en/my-first-page.md
```

Fügen Sie dieses Markdown dort ein, wo das Bild erscheinen soll:

```markdown
![Eine kurze Beschreibung des Bildes](/images/my-image.png)
```

Speichern Sie die Datei. Wenn Ihr lokaler Server läuft, sollte die Vorschau automatisch aktualisiert werden.

## Warum der Pfad mit / beginnt

Dateien in `public/` sind vom Website-Stammverzeichnis aus verfügbar.

Das bedeutet, dass diese Datei:

```text
public/images/my-image.png
```

Folgendermaßen referenziert wird:

```markdown
![Eine kurze Beschreibung des Bildes](/images/my-image.png)
```

Fügen Sie `public` nicht in den Markdown-Pfad ein.

## Nützliche Bildbeschreibungen schreiben

Der Text in den eckigen Klammern wird Alt-Text genannt:

```markdown
![Eine kurze Beschreibung des Bildes](/images/my-image.png)
```

Schreiben Sie eine kurze Beschreibung dessen, was das Bild zeigt.

Zum Beispiel:

```markdown
![Einstellungsseite mit hervorgehobenem API-Token-Feld](/images/api-token.png)
```

Guter Alt-Text hilft Lesern, die Bildschirmlesegeräte verwenden, und liefert Kontext, falls ein Bild nicht geladen werden kann.

## Was ist mit Logos?

Das Starter-Projekt hat auch diesen Ordner:

```text
config/assets/
```

Dieser Ordner ist für Website-weite Bilder wie das Logo in der Kopfzeile. Sie müssen ihn noch nicht ändern.

Später wird die Seite [Assets und Branding](/de/configuration/assets-and-branding) Logo- und Favicon-Dateien erklären.

## Nächster Schritt

[Mehr über das Schreiben von Inhalten erfahren](/de/writing-content/markdown-basics).
