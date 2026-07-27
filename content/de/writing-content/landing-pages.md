---
title: Landing-Pages
description: Erstellen Sie vollbreite Seiten für Startseiten und Übersichtsseiten.
---

Die meisten Mordoc-Seiten verwenden das normale Dokumentations-Layout: Seitenleiste links, Seiteninhalt in der Mitte und ein Inhaltsverzeichnis rechts.

Manchmal benötigen Sie eine andere Art von Seite. Eine Startseite oder Produktübersicht funktioniert oft besser als Landing-Page.

## Was eine Landing-Page verändert

Eine Landing-Page ist vollbreit.

Sie zeigt nicht:

* Die Seitennavigation
* Das rechte Inhaltsverzeichnis
* Den normalen Artikel-Header

Das macht sie nützlich für Seiten, die die Website vorstellen, Karten zeigen oder Leser in die Hauptdokumentation führen.

## Eine Seite in eine Landing-Page umwandeln

Fügen Sie `layout: landing` zum Seiten-Frontmatter hinzu:

```markdown
---
title: Startseite
description: Willkommen bei meiner Dokumentation.
layout: landing
---
```

Verwenden Sie Landing-Pages sparsam. Die meisten Dokumentationsseiten sollten das normale Layout verwenden.

## Einen Hero hinzufügen

Ein Hero ist ein großer Eröffnungsbereich, der in der Regel oben auf einer Landing-Page verwendet wird.

```markdown
{% hero
  title="Meine Produkt-Dokumentation"
  titleAccent="leicht gemacht"
  description="Finden Sie Anleitungen, Referenzmaterial und praktische Beispiele."
  background="#120b08"
%}
{% button path="/getting-started/create-project" %}
Jetzt starten
{% /button %}
{% /hero %}
```

Das `title`-Attribut ist erforderlich. Andere Felder sind optional.

Ein Hero kann folgendes verwenden:

* `title` für den Haupttext
* `titleAccent` für hervorgehobenen Titeltext
* `description` für unterstützenden Text
* `image` für ein Hero-Bild
* `background` für eine Farbe oder einen Bildpfad
* `titleColor`, `titleAccentColor` und `descriptionColor` für Textfarben

## Abschnitte hinzufügen

Verwenden Sie Abschnitte, um Landing-Page-Inhalte zu gruppieren:

```markdown
{% section title="Wählen Sie, wo Sie beginnen möchten" background="subtle" %}
Dieser Abschnitt stellt die Hauptwege durch die Dokumentation vor.
{% /section %}
```

Der `background`-Wert kann `subtle`, eine Farbe oder ein Bildpfad sein.

Der `title`-Wert ist bei Abschnitten optional, aber in der Regel hilfreich.

## Karten zu einer Landing-Page hinzufügen

Landing-Pages verwenden häufig Karten, um Leser zu führen:

```markdown
{% section title="Die Dokumentation erkunden" %}
{% cardGrid cols="3" %}
{% card title="Erste Schritte" path="/getting-started/create-project" tag="Hier starten" %}
Erstellen und starten Sie Ihr erstes Projekt.
{% /card %}

{% card title="Inhalte schreiben" path="/writing-content/markdown-basics" %}
Lernen Sie die Schreibgrundlagen.
{% /card %}

{% card title="Konfiguration" path="/configuration/site-configuration" %}
Passen Sie Ihre Website-Einstellungen an.
{% /card %}
{% /cardGrid %}
{% /section %}
```

## Schaltflächen hinzufügen

Schaltflächen sind nützlich für wichtige Handlungsaufforderungen:

```markdown
{% button path="/getting-started/create-project" %}
Ein Projekt erstellen
{% /button %}
```

Verwenden Sie `variant="secondary"` für eine dezentere Schaltfläche:

```markdown
{% button path="/writing-content/markdown-basics" variant="secondary" %}
Markdown lernen
{% /button %}
```

Der `path`-Wert ist für Schaltflächen erforderlich. Der `variant`-Wert ist optional und kann `primary` oder `secondary` sein.

## Wann eine Landing-Page verwenden

Verwenden Sie eine Landing-Page für:

* Die Startseite
* Eine Produktübersicht
* Eine Übersicht eines Hauptabschnitts

Verwenden Sie eine normale Seite für:

* Schritt-für-Schritt-Anleitungen
* Referenzseiten
* Fehlerbehebungsseiten
* Detaillierte Erklärungen

## Nächster Schritt

* [Diagramme erstellen](/de/creating-diagrams/overview).
