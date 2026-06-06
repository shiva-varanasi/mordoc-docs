---
title: Website bauen
description: Verwandeln Sie Ihr Mordoc-Projekt in eine fertige statische Website, die zur Veröffentlichung bereit ist.
---

Wenn Sie bereit zur Veröffentlichung sind, muss Mordoc eine Produktionsversion Ihrer Dokumentationswebsite erstellen.

Dieser Schritt wird Build genannt.

## Den Build ausführen

Führen Sie aus Ihrem Projektordner heraus folgenden Befehl aus:

```bash
npm run build
```

Mordoc liest Ihre Inhalte und Konfiguration und erstellt dann eine fertige Website in `dist/`.

Das Bauen veröffentlicht Ihre Website nicht. Es bereitet nur die Dateien vor, die Sie später hochladen werden.

## Was der Build erstellt

Während des Builds liest Mordoc:

* Markdown-Seiten aus `content/`
* Wendet Ihre Website-Einstellungen aus `config/` an
* Rendert jede Seite als statisches HTML
* Kopiert Bilder und Dateien aus `public/`
* Kopiert Branding-Dateien aus `config/assets/`
* Erstellt einen Suchindex für die Website-Header-Suche
* Schreibt `sitemap.xml` und `robots.txt`

Das Ergebnis ist eine statische Website. Jede Seite ist eine Datei, die ein Webserver direkt ausliefern kann.

## Der dist-Ordner

Nach einem erfolgreichen Build erstellt Mordoc:

```text
dist/
```

Dieser Ordner enthält Ihre fertige Dokumentationswebsite.

Zum Beispiel:

```text
dist/
├── index.html
├── lore/
│   └── index.html
├── sitemap.xml
├── robots.txt
├── pagefind/
└── assets/
```

Bearbeiten Sie Dateien in `dist/` nicht manuell. Wenn Sie die Website ändern müssen, bearbeiten Sie die Quelldateien in `content/`, `config/` oder `public/` und bauen Sie dann erneut.

## baseUrl vor dem Build festlegen

Stellen Sie vor der Veröffentlichung sicher, dass `config/site.json` die korrekte öffentliche URL in `baseUrl` hat:

```json
{
  "baseUrl": "https://docs.example.com"
}
```

Mordoc verwendet diesen Wert, wenn er während des Builds `sitemap.xml`, `robots.txt` und Seiten-Metadaten generiert.

Verwenden Sie Ihre echte Produktionsadresse, keine lokale Vorschau-Adresse wie `http://localhost:5173`.

Lesen Sie [Website-Konfiguration](/de/configuration/site-configuration), wenn Sie diese Einstellung aktualisieren müssen.

## Nächster Schritt

[Die gebaute Website als Vorschau anzeigen](/de/publishing/preview-before-publishing).
