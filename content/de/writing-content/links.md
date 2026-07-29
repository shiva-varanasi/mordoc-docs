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

Externe Links funktionieren auf die gleiche Weise; verwenden Sie einfach die vollständige URL:

```markdown
[Mordoc auf GitHub](https://github.com/shiva-varanasi/mordoc)
```

Sie müssen Mordoc nicht extra mitteilen, um welche Art von Link es sich handelt. Es betrachtet das Link-Ziel selbst: Ein relativer Pfad wie `/my-first-page` wird als interner Link behandelt und führt Leser sofort zur neuen Seite, ohne die Seite komplett neu zu laden, während eine vollständige URL, die mit `https://` beginnt, als extern behandelt wird und sich in einem neuen Tab öffnet.

## Zu einem Abschnitt auf der Seite verlinken

Um zu einer bestimmten Überschrift zu verlinken, fügen Sie `#` gefolgt vom Überschriftentext in Kleinbuchstaben hinzu, wobei Leerzeichen durch Bindestriche ersetzt werden. Dies verlinkt zum Beispiel zur oben stehenden Überschrift „Grundlegende Links":

```markdown
[Zu Grundlegende Links springen](#grundlegende-links)
```

Sie können auf die gleiche Weise zu einer Überschrift auf einer anderen Seite verlinken: Kombinieren Sie die Seitenadresse mit dem `#`-Anker. Dies verlinkt zum Beispiel zur Überschrift „Wie Seitenadressen erstellt werden" auf der Seite Routen und Links:

```markdown
[Wie Seitenadressen erstellt werden](/de/getting-started/routes-and-links#wie-seitenadressen-erstellt-werden)
```

## Links mit Variablen

Manchmal sollte das Ziel eines Links aus einem wiederverwendbaren Wert stammen, anstatt direkt geschrieben zu werden, zum Beispiel eine Support-URL, die sich später ändern könnte. Siehe [Variablen](/de/configuration/variables), um zu erfahren, wie Sie eine Variable definieren und in einem Link verwenden.

## Nächster Schritt

* [Bilder hinzufügen](/de/writing-content/images).
