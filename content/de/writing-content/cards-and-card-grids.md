---
title: Karten und Karten-Raster
description: Erstellen Sie visuelle Linkgruppen mit Karten und Karten-Rastern.
---

Karten sind nützlich, wenn Sie Leser zu einigen verwandten Seiten oder Optionen führen möchten.

Eine Karte ist ein kleiner Inhaltsblock. Ein Karten-Raster ordnet mehrere Karten zusammen an.

## Karten für Auswahlmöglichkeiten verwenden

Verwenden Sie Karten, wenn ein Leser wählen muss, wohin er als nächstes gehen möchte.

Eine Startseite könnte zum Beispiel zu den wichtigsten Abschnitten verlinken:

```markdown
{% cardGrid cols="3" %}
{% card title="Erste Schritte" path="/getting-started/create-project" %}
Erstellen Sie Ihr erstes Mordoc-Projekt.
{% /card %}

{% card title="Inhalte schreiben" path="/writing-content/markdown-basics" %}
Lernen Sie, wie Sie Seiten schreiben.
{% /card %}

{% card title="Konfiguration" path="/configuration/site-configuration" %}
Passen Sie Ihre Dokumentationswebsite an.
{% /card %}
{% /cardGrid %}
```

## Ein Karten-Raster hinzufügen

Beginnen Sie mit einem `cardGrid`:

```markdown
{% cardGrid cols="3" %}
{% /cardGrid %}
```

Der `cols`-Wert steuert, wie viele Spalten das Raster auf breiten Bildschirmen anzeigen soll. Übliche Werte sind `2` und `3`.

Mordoc passt das Layout auf kleineren Bildschirmen weiterhin an.

## Karten innerhalb des Rasters hinzufügen

Jede Karte benötigt ein `title`-Attribut:

```markdown
{% cardGrid cols="2" %}
{% card title="Installieren" path="/guides/install" %}
Installieren Sie das Produkt und prüfen Sie, ob es läuft.
{% /card %}

{% card title="Konfigurieren" path="/guides/configure" %}
Passen Sie die Einstellungen für Ihr Projekt an.
{% /card %}
{% /cardGrid %}
```

Verwenden Sie `path`, wenn die Karte irgendwohin verlinken soll.

Das `title`-Feld ist erforderlich. Die anderen Karten-Felder sind optional.

## Icons oder Bilder hinzufügen

Sie können ein Icon hinzufügen:

```markdown
{% card title="Sicherheit" path="/security" icon="/images/icons/shield.svg" %}
Sicherheitsempfehlungen überprüfen.
{% /card %}
```

Sie können auch ein Bild hinzufügen:

```markdown
{% card title="Versionshinweise" path="/releases" image="/images/releases.png" %}
Sehen Sie, was sich in der neuesten Version geändert hat.
{% /card %}
```

Dateien für `icon` und `image` gehören in `public/`.

## Ein kleines Tag hinzufügen

Verwenden Sie `tag` für kurze Beschriftungen wie `Neu`, `Hier starten` oder `Empfohlen`.

```markdown
{% card title="Schnellstart" path="/quickstart" tag="Hier starten" %}
Beginnen Sie mit dem schnellsten Weg durch die Dokumentation.
{% /card %}
```

Verwenden Sie Tags sparsam. Wenn jede Karte ein Tag hat, verlieren die Tags ihre Wirkung.

## Karten-Optionen

Karten unterstützen diese Felder:

* `title` ist erforderlich und wird zur Kartenüberschrift.
* `path` lässt die Karte zu einer anderen Seite oder Website verlinken.
* `icon` zeigt ein kleines Icon.
* `image` zeigt ein größeres Bild.
* `tag` zeigt eine kurze Beschriftung wie `Neu` oder `Hier starten`.

Verwenden Sie nur die Felder, die Lesern helfen zu wählen, wohin sie als nächstes gehen möchten.

Karten-Raster unterstützen `cols`, das die bevorzugte Spaltenanzahl auf breiten Bildschirmen steuert.

## Kartentext kurz halten

Kartentext sollte Lesern bei der Wahl helfen. Ein kurzer Satz ist in der Regel ausreichend.

## Nächster Schritt

[Landing-Pages erstellen](/de/writing-content/landing-pages).
