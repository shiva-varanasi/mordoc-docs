---
title: Benutzerdefinierte Head-Skripte
description: Fügen Sie Skripte von Drittanbietern, wie Analytics oder Cookie-Consent-Banner, in den HTML-Head jeder Seite ein.
---

Mordoc rendert Ihr `content/`-Markdown für Sie in HTML. Das bedeutet, es gibt keine Seite, auf der Sie einen `<script>`-Tag von Hand direkt in `<head>` schreiben können.

Manche Skripte müssen trotzdem dorthin. Analytics, ein Cookie-Consent- oder Datenschutz-Banner eines Drittanbieters oder ein von Ihrem Unternehmen selbst entwickeltes Snippet sind gängige Beispiele. `config/custom-head.html` ist der Ort dafür.

## Die Datei hinzufügen

Erstellen Sie sie hier:

```text
config/custom-head.html
```

Die Datei ist optional. Existiert sie nicht, überspringt Mordoc sie, und nichts ändert sich.

Fügen Sie darin das HTML ein, das das Skript benötigt. Zum Beispiel ein Analytics-Snippet eines Drittanbieters:

```html
<script defer src="https://analytics.example.com/script.js" data-site-id="your-site-id"></script>
```

## Wie Mordoc sie verwendet

Mordoc fügt den Inhalt der Datei in den `<head>` jeder Seite ein, sowohl in `mordoc dev` als auch in `mordoc build`. Mordocs eigene Tags, wie `<title>` sowie seine Meta- und Open-Graph-Tags, sind bereits vorhanden, bevor Ihr Inhalt hinzugefügt wird.

{% callout type="warning" title="Inhalt wird unverändert eingefügt" %}
Mordoc prüft oder verändert den Inhalt von `config/custom-head.html` nicht. Er wird genau so eingefügt, wie er geschrieben wurde, auf jeder Seite, für jeden Besucher. Fügen Sie nur Skripte aus Quellen hinzu, denen Sie vertrauen.
{% /callout %}

## Nächster Schritt

- [Änderungsmanagement mit Git](/de/publishing/change-management).
