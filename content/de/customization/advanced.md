---
title: Erweitert
description: Zielen Sie mit Design-Tokens auf einzelne Teile von Mordocs Oberfläche, vom gesamten Seitenlayout bis hinunter zu einer einzelnen Komponente.
---

Die grundlegende Anpassung ändert eine Farbe und optional eine Schriftart. Die erweiterte Anpassung geht weiter: Jeder visuelle Teil einer Mordoc-Website, bis hinunter zu einer einzelnen Schaltfläche oder einem einzelnen Callout, hat seinen eigenen Satz von Design-Tokens, die Sie überschreiben können, ohne die tatsächliche Struktur oder das Verhalten einer Komponente anzufassen.

## Wie Überschreibungen geschichtet sind

Das CSS einer Mordoc-Website ist aus drei Schichten aufgebaut, in dieser Reihenfolge:

1. **Mordocs Standardwerte**: das eingebaute Erscheinungsbild, sodass eine neue Website ohne jede Konfiguration bereits funktioniert.
2. **`config/styles/theme.css`**: Ihre website-weiten Überschreibungen aus der [Grundlegenden Anpassung](/de/customization/basic): `--accent` und die Handvoll globaler Tokens, die unter [Design Tokens](/de/customization/advanced/design-tokens) behandelt werden.
3. **`config/styles/<component>.css`**: eine optionale Datei pro Komponente, jede überschreibt nur die eigenen Tokens dieser Komponente.

Jede Schicht muss nur die Werte enthalten, die Sie ändern möchten. Eine spätere Schicht gewinnt gegenüber einer früheren, sodass eine in `theme.css` festgelegte Farbe überall zum Standard dieser Komponente wird, und eine in der eigenen Datei der Komponente festgelegte Farbe nur für diese Komponente gewinnt. Wenn eine Datei nicht existiert, überspringt Mordoc sie einfach. Nichts geht kaputt.

## Eine Seite pro Datei, eine Datei pro Teil der Oberfläche

Jede Seite in diesem Abschnitt dokumentiert genau eine Datei unter `config/styles/`, und jede Datei zielt auf genau einen Teil der Oberfläche, dieselbe Eins-zu-eins-Zuordnung, die Mordoc intern verwendet. Wenn Sie `config/styles/header.css` geöffnet haben, ist [Header](/de/customization/advanced/header) die Seite, die jeden Token dokumentiert, den Sie darin setzen können.

## So lesen, wie Mordoc aufgebaut ist

Die Seiten sind so geordnet, dass sie widerspiegeln, wie Mordocs eigene Oberfläche zusammengesetzt ist, indem sie sich Ebene für Ebene hineinzoomen:

1. **[Design Tokens](/de/customization/advanced/design-tokens)**: die übrigen globalen Farben, über `--accent` hinaus, auf die alles andere standardmäßig zurückgreift.
2. **[App Layout](/de/customization/advanced/app-layout)**: die drei Boxen, aus denen jede Seite aufgebaut ist: der Header, die Seitennavigation und der Inhaltsbereich.
3. **Header und alles darin**: das eigene Grundgerüst des Headers, dann jedes Teil, aus dem er besteht: Header-Links, obere Navigation, die Sprachauswahl, der Theme-Umschalter und die Suche.
4. **Seitennavigation**: die Seitenleisten-Box daneben.
5. **Content und alles darin**: das eigene Grundgerüst des Inhaltsbereichs, dann die Artikelseite, das Inhaltsverzeichnis und jede Komponente, die Sie auf einer Markdown-Seite platzieren können: Callouts, Karten, Code-Blöcke, Diagramme, Bilder und die Landing-Page-Bausteine (Hero, Abschnitte, Schaltflächen).

Sie müssen nicht jede Seite lesen. Springen Sie direkt zu dem einen Teil der Oberfläche, den Sie ändern möchten. Seine Seite listet nur die Tokens auf, die für ihn gelten.

## Nächster Schritt

- [Globale Design-Tokens festlegen](/de/customization/advanced/design-tokens).
