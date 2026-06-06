---
title: SEO und Suche
description: Verstehen Sie, wie Mordoc Suchmaschinen, soziales Teilen und die integrierte Website-Suche unterstützt.
---

Mordoc hilft Ihrer Dokumentationswebsite, in Suchergebnissen, Link-Vorschauen und der integrierten Website-Suche gut zu funktionieren.

Das meiste davon geschieht automatisch, wenn Sie die Website bauen. Einige Einstellungen in Ihrem Projekt helfen Suchmaschinen und sozialen Netzwerken, Ihre Inhalte zu verstehen.

## Nützliche Seitenbeschreibungen schreiben

Jede Seite kann eine optionale `description` in ihrem Frontmatter enthalten:

```markdown
---
title: Install the App
description: Install the app and confirm it runs on your machine.
---
```

Wenn Sie die Website bauen, verwendet Mordoc diesen Wert auf zwei Arten:

* Es fügt für diese Seite ein `<meta name="description">`-Tag hinzu.
* Es verwendet die Seitenbeschreibung in Open-Graph- und Twitter-Vorschau-Tags.

Wenn eine Seite keine `description` hat, fügt Mordoc für diese Seite kein `<meta name="description">` hinzu.

Für Social-Preview-Tags greift Mordoc auf die website-weite `description` aus `config/site.json` zurück.

Auf normalen Dokumentationsseiten erscheint die Beschreibung auch unter dem Seitentitel für Leser. Landing-Pages zeigen die Frontmatter-Beschreibung nicht auf der Seite selbst an, sie kann aber trotzdem in den gebauten Seiten-Metadaten verwendet werden, wenn Sie sie angeben.

## Website-weite Metadaten festlegen

Website-weite Sharing-Einstellungen befinden sich in `config/site.json`.

Die wichtigsten Felder für die Veröffentlichung sind:

* `name` und `description` für die gesamte Website
* `baseUrl` für die öffentliche Website-Adresse
* `metadata.ogImage` für das Bild, das erscheint, wenn jemand Ihren Website-Link teilt

Zum Beispiel:

```json
{
  "name": "Acme Docs",
  "description": "Guides and reference material for Acme users.",
  "baseUrl": "https://docs.example.com",
  "metadata": {
    "ogImage": "/images/ring-og.svg",
    "ogType": "website",
    "twitterCard": "summary_large_image",
    "twitterSite": "@example"
  }
}
```

Der `ogImage`-Pfad verweist auf eine Datei in `public/`, zum Beispiel:

```text
public/images/ring-og.svg
```

Eine vollständige Erklärung dieser Felder finden Sie unter [Website-Konfiguration](/de/configuration/site-configuration).

## Was Mordoc zur Build-Zeit generiert

Wenn Sie `npm run build` ausführen, fügt Mordoc SEO- und Such-Dateien zu `dist/` hinzu.

### Seiten-Metadaten

Jede gebaute Seite enthält Metadaten wie:

* Einen Seitentitel im Format `Seitentitel — Website-Name`
* Ein Seitenbeschreibungs-Meta-Tag, wenn das Frontmatter der Seite eine `description` enthält
* Kanonische Links basierend auf `baseUrl`
* Open-Graph-Tags, einschließlich `og:description`
* Twitter-Card-Tags, wenn `metadata.twitterCard` in `config/site.json` festgelegt ist

Wenn eine Seite keine Frontmatter-Beschreibung hat, können Social-Preview-Tags weiterhin die website-weite Beschreibung aus `config/site.json` verwenden.

### sitemap.xml

Mordoc schreibt `dist/sitemap.xml` mit einem URL-Eintrag für jede Seite in Ihrem Projekt.

Suchmaschinen verwenden diese Datei, um Ihre Dokumentationsseiten zu entdecken.

Die URLs stammen aus Ihren Inhaltsdateien und `baseUrl`.

### robots.txt

Mordoc schreibt auch `dist/robots.txt`.

Diese Datei teilt Suchmaschinen mit, dass sie Ihre Website crawlen dürfen, und verweist sie auf `sitemap.xml`.

### Suchindex

Mordoc verwendet [Pagefind](https://pagefind.app/) für die Website-interne Suche.

Pagefind ist ein statisches Such-Werkzeug. Es liest Ihre gebauten HTML-Seiten und erstellt einen Suchindex, der vollständig im Browser läuft. Das bedeutet, Leser können Ihre Dokumentation durchsuchen, ohne einen separaten Such-Server zu benötigen.

Wenn Sie `npm run build` ausführen, erstellt Mordoc diesen Index automatisch, nachdem die statischen HTML-Dateien erstellt wurden.

Für eine einsprachige Website wird der Index geschrieben in:

```text
dist/pagefind/
```

Für mehrsprachige Websites erstellt Mordoc einen Index pro Sprache, zum Beispiel:

```text
dist/pagefind-en/
dist/pagefind-fr/
```

Dies versorgt das Suchfeld im Website-Header. Wenn ein Leser die Sprache wechselt, lädt Mordoc den passenden Index für diese Sprache.

Pagefind indiziert den Hauptseiteninhalt und die Seitentitel aus Ihren gebauten HTML-Dateien. Frontmatter-Beschreibungen werden nicht als separates Suchfeld verwendet.

Die Suche funktioniert erst nach dem Bauen der Website. Der Entwicklungsserver hat keine Such-Unterstützung.

## Nächster Schritt

[Website veröffentlichen](/de/publishing/deploy-your-site).
