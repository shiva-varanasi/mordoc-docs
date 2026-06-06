---
title: Seiten schreiben
description: Nehmen Sie Ihre erste Inhaltsänderung an einer Mordoc-Seite vor.
---

Jetzt, da Sie die Projektstruktur kennengelernt haben, ist es Zeit, eine Seite zu ändern.

Sie müssen noch nicht die gesamte Mordoc-Schreibsyntax lernen. Beginnen Sie mit einer kleinen Bearbeitung und sehen Sie sich die Vorschau dann im Browser an.

## Eine Beispielseite öffnen

Öffnen Sie in Ihrem Projekt diese Datei:

```text
content/en/lore.md
```

Dies ist eine der fiktiven Seiten aus der Starter-Vorlage.

## Einen Satz ändern

Suchen Sie einen Satz im Seitentext und ersetzen Sie ihn durch etwas Einfaches.

Sie könnten zum Beispiel einen Starter-Text ersetzen durch:

```markdown
Dies ist meine erste Mordoc-Seitenbearbeitung.
```

Speichern Sie die Datei.

Wenn Ihr lokaler Server noch aus dem vorherigen Schritt läuft, sollte die Browser-Vorschau automatisch aktualisiert werden. Wenn der Server nicht läuft, starten Sie ihn erneut:

```bash
npm run dev
```

## Die Seitenteile kennenlernen

Eine Mordoc-Seite besteht aus zwei Hauptteilen:

```markdown
---
title: Lore of the Ring
description: A short history of the One Ring and the forces bound to it.
---

Dies ist der Seiteninhalt.

## Bevor Sie beginnen

Dies ist ein Abschnitt innerhalb der Seite.
```

Der Teil zwischen den `---`-Zeilen wird Frontmatter genannt. Er gibt Mordoc Informationen über die Seite.

Der Text unterhalb des Frontmatters ist der Seiteninhalt. Hier befinden sich Ihre Absätze, Listen, Links, Bilder, Callouts, Karten und andere Inhalte.

Der Abschnitt [Inhalte schreiben](/de/writing-content/markdown-basics) wird die Schreibsyntax später im Detail erklären.

## Das title-Feld

Jede Seite benötigt einen `title` in ihrem Frontmatter:

```yaml
title: Lore of the Ring
```

Mordoc verwendet diesen als Hauptseitenüberschrift. Da der Titel bereits zur Hauptüberschrift wird, beginnen Sie Überschriften im Seiteninhalt mit `##`, nicht mit `#`.

Zum Beispiel:

```markdown
## Bevor Sie beginnen

Schreiben Sie hier Ihren Abschnittsinhalt.
```

## Das description-Feld

Das `description`-Feld ist optional, aber es ist eine gute Gewohnheit, es einzufügen:

```yaml
description: A short history of the One Ring and the forces bound to it.
```

Verwenden Sie einen kurzen Satz, der erklärt, worum es auf der Seite geht. Mordoc kann ihn für Seiteninformationen und Suchmaschinen-Vorschauen verwenden.

Die Seite [Frontmatter-Referenz](/de/reference/frontmatter) wird später alle unterstützten Frontmatter-Felder auflisten.

## Eine neue Seite erstellen

Nachdem Sie sich mit dem Bearbeiten einer vorhandenen Seite vertraut gemacht haben, erstellen Sie eine neue Markdown-Datei:

```text
content/en/my-first-page.md
```

Fügen Sie diesen Inhalt hinzu:

```markdown
---
title: My First Page
description: A simple test page for learning Mordoc.
---

This is my first new page.

## What I am learning

I am learning how Mordoc turns Markdown files into documentation pages.
```

Dadurch wird eine Seite unter folgendem Pfad erstellt:

```text
/my-first-page
```

{% callout type="note" title="Warum sie möglicherweise noch nicht in der Seitenleiste erscheint" %}
Das Erstellen der Datei erstellt die Seitenroute, fügt die Seite jedoch nicht automatisch zur Seitenleiste hinzu. Die Navigation wird separat gesteuert, damit Sie wählen können, welche Seiten im Menü erscheinen.
{% /callout %}

## Nächster Schritt

[Erfahren Sie, wie Routen und Links funktionieren](/de/getting-started/routes-and-links).
