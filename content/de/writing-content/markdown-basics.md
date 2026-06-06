---
title: Markdown-Grundlagen
description: Lernen Sie die grundlegenden Markdown-Muster, die in Mordoc-Seiten verwendet werden.
---

Markdown ist das Klartextformat, mit dem Sie Mordoc-Seiten schreiben. Es ermöglicht Ihnen, zuerst lesbaren Text zu schreiben und dann einfache Zeichen für Überschriften, Listen, Links, Bilder und Code-Beispiele hinzuzufügen.

Sie müssen nicht alles auf einmal lernen. Beginnen Sie mit den Mustern auf dieser Seite und kehren Sie zurück, wenn Sie sie benötigen.

## Mit Frontmatter beginnen

Jede Mordoc-Seite beginnt mit Frontmatter:

```markdown
---
title: My First Page
description: A simple test page for learning Mordoc.
---
```

Das `title`-Feld ist erforderlich. Mordoc verwendet es als Hauptseitenüberschrift.

Das `description`-Feld ist optional, aber es ist eine gute Gewohnheit, es einzufügen. Es hilft dabei, die Seite in Suchergebnissen und Seiten-Metadaten zu beschreiben.

Landing-Pages können auch `layout: landing` verwenden. Mehr dazu erfahren Sie unter [Landing-Pages](/de/writing-content/landing-pages).

## Absätze schreiben

Schreiben Sie unterhalb des Frontmatters normalen Text:

```markdown
Dies ist der erste Absatz.

Dies ist ein weiterer Absatz.
```

Lassen Sie eine Leerzeile zwischen den Absätzen.

## Abschnitte hinzufügen

Da der Frontmatter-Titel bereits zur Hauptseitenüberschrift wird, beginnen Sie Überschriften im Seiteninhalt mit `##`.

```markdown
## Bevor Sie beginnen

Schreiben Sie hier den Abschnittsinhalt.

## Nächste Schritte

Schreiben Sie hier den nächsten Abschnitt.
```

Verwenden Sie Überschriften, um eine Seite in klare Abschnitte zu unterteilen. Vermeiden Sie es, von `##` zu `####` zu springen; wenn Sie einen kleineren Abschnitt innerhalb eines Abschnitts benötigen, verwenden Sie `###`.

## Listen hinzufügen

Verwenden Sie Aufzählungslisten, wenn die Reihenfolge keine Rolle spielt:

```markdown
* Ein Projekt erstellen
* Eine Seite bearbeiten
* Die Website als Vorschau anzeigen
```

Verwenden Sie nummerierte Listen, wenn die Reihenfolge wichtig ist:

```markdown
1. Öffnen Sie den Projektordner.
2. Bearbeiten Sie eine Markdown-Datei.
3. Speichern Sie die Datei.
```

## Links hinzufügen

Verwenden Sie die Seitenadresse, wenn Sie zu einer anderen Seite verlinken:

```markdown
[Meine erste Seite lesen](/my-first-page)
```

Verlinken Sie nicht zur Markdown-Datei selbst:

```markdown
[Meine erste Seite lesen](./my-first-page.md)
```

Die Seite [Routen und Links](/de/getting-started/routes-and-links) erklärt, warum Mordoc-Links Seitenadressen verwenden.

## Bilder hinzufügen

Legen Sie Inhaltsbilder in `public/` ab und referenzieren Sie sie mit einem Pfad, der mit `/` beginnt.

```markdown
![Eine kurze Beschreibung des Bildes](/images/my-image.png)
```

Die Seite [Bilder und Dateien](/de/getting-started/images-and-files) zeigt diesen Schritt im Detail.

## Code-Beispiele hinzufügen

Verwenden Sie Backticks für kurzen Inline-Code:

```markdown
Führen Sie `npm run dev` aus, um den lokalen Server zu starten.
```

Verwenden Sie einen umzäunten Code-Block für längere Beispiele:

````markdown
```javascript
const productName = "Mordoc";
const message = `Welcome to ${productName}`;
console.log(message);
```
````

Fügen Sie den Sprachnamen nach den öffnenden Backticks hinzu, wenn Sie ihn kennen. Mordoc verwendet diesen für die Syntaxhervorhebung.

## Nächster Schritt

[Callouts verwenden](/de/writing-content/callouts).
