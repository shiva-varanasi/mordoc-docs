---
title: Website veröffentlichen
description: Veröffentlichen Sie den gebauten dist-Ordner in der Hosting-Umgebung Ihres Unternehmens.
---

Eine Mordoc-Website zu veröffentlichen bedeutet, die gebauten Dateien aus `dist/` in Ihre Hosting-Umgebung hochzuladen.

Sie veröffentlichen Ihre Markdown-Dateien oder Konfigurationsordner nicht direkt.

## Was Sie veröffentlichen

Veröffentlichen Sie alles innerhalb von:

```text
dist/
```

Dieser Ordner wurde erstellt, als Sie [Ihre Website gebaut haben](/de/publishing/build-your-site). Er enthält die vollständige statische Website, einschließlich HTML-Seiten, Assets, Such-Dateien, `sitemap.xml` und `robots.txt`.

Laden Sie nicht hoch:

* `content/`
* `config/`
* `public/`
* `node_modules/`
* Quell-Projektdateien

Leser sollten nur die gebaute Website aus `dist/` erhalten.

## Wie statisches Hosting funktioniert

Mordoc erstellt eine statische Website.

Das bedeutet:

* Seiten werden als Dateien ausgeliefert
* Kein Anwendungsserver muss Ihre Dokumentation betreiben
* Ein Webserver oder CDN kann die Website direkt hosten

Ihr Infrastruktur-Team verwendet möglicherweise Objektspeicher, ein CDN, einen statischen Hosting-Dienst oder einen einfachen Webserver. Das genaue Werkzeug hängt von Ihrem Unternehmen ab.

Das Wichtige ist in jedem Fall dasselbe: Veröffentlichen Sie den Inhalt von `dist/`.

## Typische Schritte zur Veröffentlichung

Die meisten Teams folgen einem Ablauf wie diesem:

1. [Die Website bauen](/de/publishing/build-your-site)
2. [Die gebaute Website lokal als Vorschau anzeigen](/de/publishing/preview-before-publishing)
3. Den Inhalt von `dist/` hochladen oder veröffentlichen
4. Ihre öffentliche Dokumentations-URL auf die gehosteten Dateien verweisen

Wenn Ihr Team Continuous Deployment verwendet, kann der Build-Schritt automatisch ausgeführt werden, wenn Änderungen zusammengeführt werden. Der Veröffentlichungsschritt publiziert weiterhin die generierte `dist/`-Ausgabe.

## Die Live-Website überprüfen

Überprüfen Sie nach der Veröffentlichung Ihre öffentliche Dokumentations-URL und prüfen Sie:

* Die Startseite lädt
* Seitenleisten- und obere Navigations-Links funktionieren
* Bilder, Logos und Downloads laden korrekt
* Die Suche liefert erwartete Ergebnisse
* Geteilte Links zeigen den richtigen Titel und das richtige Vorschaubild

Wenn etwas fehlt, korrigieren Sie das Quellprojekt, bauen Sie neu und veröffentlichen Sie den aktualisierten `dist/`-Ordner erneut.

## baseUrl aktuell halten

Stellen Sie sicher, dass `baseUrl` in `config/site.json` mit der Live-Website-Adresse übereinstimmt, bevor Sie für die Produktion bauen.

Wenn sich die Adresse später ändert, aktualisieren Sie `baseUrl`, bauen Sie neu und veröffentlichen Sie erneut.

Dies hält kanonische Links, `sitemap.xml` und Social-Vorschauen auf die korrekte Website ausgerichtet.

## Sie sind bereit

Sie haben jetzt einen vollständigen Weg vom Schreiben von Inhalten bis zur Veröffentlichung einer Unternehmensdokumentationswebsite mit Mordoc.

Wenn Sie die Quellprojekte hinter Mordoc selbst nachschlagen müssen, lesen Sie [Quell-Repositories](/de/references/github-repo).
