---
title: Links
description: Verlinken Sie zu anderen Seiten, externen Websites und variablenbasierten Zielen.
---

Links verweisen einen Leser auf eine andere Seite Ihrer Website, eine externe Website oder einen Anker innerhalb der aktuellen Seite.

## Grundlegende Links

Verwenden Sie die Seitenadresse, wenn Sie zu einer anderen Seite verlinken:

```markdown
[Meine erste Seite lesen](/my-first-page)
```

Verlinken Sie nicht zur Markdown-Datei selbst:

```markdown
[Meine erste Seite lesen](./my-first-page.md)
```

Die Seite [Routen und Links](/de/getting-started/routes-and-links) erklärt, warum Mordoc-Links Seitenadressen verwenden.

Externe Links funktionieren auf die gleiche Weise — verwenden Sie einfach die vollständige URL:

```markdown
[Mordoc auf GitHub](https://github.com/shiva-varanasi/mordoc)
```

## Links mit Variablen

Das Ziel eines einfachen Markdown-Links wird als reiner Text analysiert, sodass eine darin enthaltene Variable nie aufgelöst wird:

```markdown
[Support kontaktieren]($SUPPORT_PORTAL_URL)
```

Dies zeigt den literalen Text `$SUPPORT_PORTAL_URL` an, nicht den Wert aus `config/variables.yaml`.

Wenn ein Link-Ziel aus einer Variable stammen muss, verwenden Sie stattdessen den `link`-Tag:

```markdown
{% link path=$SUPPORT_PORTAL_URL %}Support kontaktieren{% /link %}
```

`path` wird gegen `config/variables.yaml` aufgelöst, genauso wie `{% $variableName %}` im laufenden Text. Siehe [Variablen](/de/configuration/variables), um zu erfahren, wie Sie eine definieren.

Verwenden Sie die Tag-Form nur, wenn das Ziel sich tatsächlich ändern muss — für gewöhnliche interne und externe Links sind einfache Markdown-Links einfacher und funktionieren genauso.

## Nächster Schritt

* [Bilder hinzufügen](/de/writing-content/images).
