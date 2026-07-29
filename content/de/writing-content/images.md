---
title: Bilder
description: Fügen Sie Bilder und Icons hinzu, einschließlich solcher mit einer variablenbasierten Quelle.
---

Legen Sie Inhaltsbilder in `public/` ab und referenzieren Sie sie dann mit einem Pfad, der mit `/` beginnt.

## Grundlegende Bilder

```markdown
![Grafik](/images/content-images/artwork.png)
```

Der Text in eckigen Klammern ist der `alt`-Text des Bildes. Halten Sie ihn beschreibend, da Bildschirmlesegeräte ihn vorlesen und er angezeigt wird, falls das Bild nicht geladen werden kann.

**So sieht das aus**

![Grafik](/images/content-images/artwork.png)

Die Seite [Bilder und Dateien](/de/getting-started/images-and-files) führt Sie Schritt für Schritt durch das Hinzufügen eines Bildes.

## Icons

Icons funktionieren genauso wie jedes andere Bild: Legen Sie die Datei in `public/` ab und referenzieren Sie dann ihren Pfad.

```text
public/icons/shield.svg
```

Kleine SVGs sind die häufigste Wahl, da sie in jeder Größe scharf bleiben.

Sie fügen ein Icon nicht direkt in den Seitentext ein. Stattdessen nehmen bestimmte Komponenten eine Icon-Datei über ein Attribut entgegen, wie zum Beispiel `icon` bei einer [Karte](/de/writing-content/cards-and-card-grids) oder das Icon eines Akteurs in einem [Sequenzdiagramm](/de/creating-diagrams/sequence-diagrams).

## Bilder mit Variablen

Manchmal sollte die Quelle eines Bildes aus einem wiederverwendbaren Wert stammen, anstatt direkt geschrieben zu werden, zum Beispiel eine Logo-URL, die sich später ändern könnte. Siehe [Variablen](/de/configuration/variables), um zu erfahren, wie Sie eine Variable definieren und in einem Bild verwenden.

## Nächster Schritt

- [Callouts verwenden](/de/writing-content/callouts).
