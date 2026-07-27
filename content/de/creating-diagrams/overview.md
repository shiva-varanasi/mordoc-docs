---
title: Diagramme
description: Erstellen Sie Diagramme direkt in Markdown, gerendert als scharfe Vektorgrafiken, die zum Design Ihrer Website passen.
---

Mit Mordoc können Sie Diagramme direkt in Markdown zeichnen, mit einer Klartext-Syntax innerhalb eines eingezäunten Codeblocks. Kein Bildexport, kein separates Diagrammtool, keine Datei, die mit der umgebenden Seite synchron gehalten werden muss — das Diagramm lebt in der Seite selbst.

## Warum nicht einfach Mermaid verwenden?

Mermaid und ähnliche Tools sind hervorragend, und Sie kennen ihre Syntax vielleicht bereits. Mordoc baut trotzdem eine eigene Diagramm-Engine, aus einigen Gründen, die speziell für die Anforderungen einer Dokumentations-Website gelten:

* **Diagramme, die aussehen wie der Rest Ihrer Website.** Mordocs Diagramme werden aus denselben Design-Tokens gebaut wie alles andere um sie herum, sodass sie automatisch zu Ihren Farben, Ihrer Typografie und dem Hell-/Dunkel-Theme passen — kein separates Theme, das konfiguriert oder synchron gehalten werden muss.
* **Keine Diagramm-Engine wird an den Browser ausgeliefert.** Mordoc parst und layoutet das Diagramm einmal, zur Build-Zeit, in Node, als nativer Teil derselben Pipeline, die auch den Rest Ihrer Inhalte verarbeitet. Die Seite liefert nur das fertige Ergebnis als Inline-SVG aus — der Browser eines Besuchers sieht niemals die Diagramm-Syntax oder eine Diagramm-Rendering-Bibliothek.
* **Es verhält sich wie der Rest Ihrer Inhalte.** Ein Mordoc-Diagramm ist anklickbar und öffnet eine zoombare Lightbox genau wie ein Bild — kein separates Interaktionsmodell, das Sie lernen müssen.

{% callout type="note" title="Zur Build-Zeit, nicht clientseitig" %}
Da Diagramme während des Builds geparst und layoutet werden, lässt ein fehlerhaftes Diagramm den Build mit einer klaren Fehlermeldung fehlschlagen — genau wie ein defekter Link in Ihrer Navigationskonfiguration — anstatt Lesern still eine leere Box auszuliefern.
{% /callout %}

## Der allgemeine Aufbau

Jedes Diagramm ist ein eingezäunter Codeblock, dessen Sprache den Diagrammtyp benennt:

````markdown
```sequence-diagram
...diagram syntax goes here...
```
````

Mordoc erkennt die Sprache, parst den Inhalt des Blocks und ersetzt ihn durch das gerenderte Diagramm — genauso wie es einen ` ```javascript `-Block durch ein syntax-hervorgehobenes Codebeispiel ersetzt, nur zu einem anderen Renderer geleitet.

## Nächster Schritt

* [Ein Sequenzdiagramm erstellen](/de/creating-diagrams/sequence-diagrams).
