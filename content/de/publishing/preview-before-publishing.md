---
title: Vorschau vor der Veröffentlichung
description: Überprüfen Sie Ihre gebaute Dokumentationswebsite lokal, bevor Sie sie veröffentlichen.
---

Nehmen Sie sich nach dem Bauen der Website einen Moment, um die Dateien in `dist/` als Vorschau anzusehen, bevor Sie sie veröffentlichen.

Dies unterscheidet sich von `npm run dev`.

## Entwicklungs- und Build-Vorschau sind unterschiedlich

Verwenden Sie beim Schreiben von Dokumentation:

```bash
npm run dev
```

Dieser Befehl ist für die tägliche Bearbeitung. Er zeigt Ihre neuesten Inhalte und Konfigurationen, während Sie arbeiten.

Nachdem Sie `npm run build` ausgeführt haben, sollten Sie stattdessen die gebauten Dateien in `dist/` als Vorschau anzeigen. Diese Vorschau zeigt dieselbe statische Website, die Sie veröffentlichen werden.

## Den dist-Ordner als Vorschau anzeigen

Bauen Sie zuerst die Website:

```bash
npm run build
```

Dann stellen Sie den `dist/`-Ordner mit einem statischen Dateiserver bereit.

Für eine schnelle lokale Überprüfung können Sie Folgendes ausführen:

```bash
npx serve dist
```

Öffnen Sie die in Ihrem Terminal angezeigte URL, in der Regel etwa:

```text
http://localhost:3000
```

Durchsuchen Sie die Website so, wie es ein Leser tun würde.

## Was überprüft werden sollte

Überprüfen Sie vor der Veröffentlichung:

* Seiten öffnen sich korrekt über die Seitenleiste und Links
* Bilder und Downloads laden wie erwartet
* Die Startseite und Landing-Pages sehen richtig aus
* Die Suche funktioniert im Website-Header
* Website-Name, Logo und Theme sehen korrekt aus

Wenn etwas nicht stimmt, korrigieren Sie die Quelldateien in Ihrem Projekt, führen Sie `npm run build` erneut aus und sehen Sie sich die Vorschau noch einmal an.

## Nächster Schritt

[SEO- und Sucheinstellungen überprüfen](/de/publishing/seo-and-search).
