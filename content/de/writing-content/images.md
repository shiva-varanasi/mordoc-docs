---
title: Bilder
description: Fügen Sie Bilder hinzu, einschließlich solcher mit einer variablenbasierten Quelle.
---

Legen Sie Inhaltsbilder in `public/` ab und referenzieren Sie sie dann mit einem Pfad, der mit `/` beginnt.

## Grundlegende Bilder

```markdown
![Eine kurze Beschreibung des Bildes](/images/my-image.png)
```

Der Text in eckigen Klammern ist der `alt`-Text des Bildes — halten Sie ihn beschreibend, da Bildschirmlesegeräte ihn vorlesen und er angezeigt wird, falls das Bild nicht geladen werden kann.

Die Seite [Bilder und Dateien](/de/getting-started/images-and-files) zeigt diesen Schritt im Detail.

## Bilder mit Variablen

Wie bei Links wird die Quelle eines einfachen Markdown-Bildes als reiner Text analysiert, sodass eine darin enthaltene Variable nie aufgelöst wird:

```markdown
![Grafik]($IMAGE_LINK)
```

Dies zeigt den literalen Text `$IMAGE_LINK` als Bildquelle an, nicht den Wert aus `config/variables.yaml`.

Wenn eine Bildquelle aus einer Variable stammen muss, verwenden Sie stattdessen den `image`-Tag. Er ist selbstschließend, da `alt` ein Attribut und kein Bildinhalt ist:

```markdown
{% image src=$IMAGE_LINK alt="Grafik" /%}
```

`src` wird gegen `config/variables.yaml` aufgelöst, genauso wie `{% $variableName %}` im laufenden Text. Siehe [Variablen](/de/configuration/variables), um zu erfahren, wie Sie eine definieren.

Verwenden Sie die Tag-Form nur, wenn die Quelle sich tatsächlich ändern muss — für gewöhnliche statische Bilder ist einfaches Markdown einfacher und funktioniert genauso.

## Nächster Schritt

[Callouts verwenden](/de/writing-content/callouts).
