---
title: Node.js installieren
description: Installieren Sie Node.js und npm, um Mordoc auszuführen und Ihre Dokumentationswebsite zu erstellen.
---

Bevor Sie Mordoc ausführen können, muss **Node.js** auf Ihrem System installiert sein. Keine Sorge, wenn das zunächst technisch klingt. Sie müssen nicht verstehen, wie Node.js intern funktioniert, um Mordoc zu verwenden.

Diese Seite erklärt, was Node.js und npm in einfachen Worten sind, und führt Sie dann durch die Installation.

## Was ist Node.js?

Node.js ist eine Laufzeitumgebung, mit der Sie JavaScript-Programme auf Ihrem Computer ausführen können.

Sie ermöglicht es Mordoc:

* Lokal auf Ihrem Rechner zu laufen
* Ihre Dokumentationswebsite zu erstellen
* Abhängigkeiten und Werkzeuge im Hintergrund zu verwalten

Sie werden kein JavaScript schreiben oder Anwendungen entwickeln. Node.js ist lediglich eine Voraussetzung, die Mordoc zum Funktionieren benötigt.

## Was ist npm?

**npm** steht für *Node Package Manager*.

Es wird zusammen mit Node.js geliefert und dient dazu:

* Werkzeuge und Pakete zu installieren (wie Mordoc)
* Vordefinierte Befehle auszuführen
* Abhängigkeiten aktuell zu halten

Sie müssen npm nicht separat installieren. Wenn Node.js installiert ist, ist npm bereits enthalten.

## Node.js herunterladen

{% callout type="note" title="Erforderliche Mindestversion" %}
Mordoc erfordert Node.js in Version **24.18.1** oder höher. Der unten stehende LTS-Download erfüllt diese Anforderung.
{% /callout %}

1. Besuchen Sie die offizielle Node.js-Website: [https://nodejs.org](https://nodejs.org)
2. Laden Sie die **LTS-Version (Long Term Support)** herunter. Dies ist die empfohlene und stabilste Option.

Wählen Sie das Installationsprogramm für Ihr Betriebssystem:

* **Windows**: Windows-Installationsprogramm herunterladen
* **macOS**: macOS-Installationsprogramm herunterladen
* **Linux**: Verwenden Sie das offizielle Paket für Ihre Distribution oder folgen Sie den Linux-Installationsanweisungen auf der Website

## Node.js installieren

Führen Sie das Installationsprogramm aus und folgen Sie den empfohlenen Optionen im Installationsassistenten.

Für die meisten Benutzer sind die Standardeinstellungen korrekt. Sie müssen nichts anpassen.

## Installation überprüfen

Überprüfen Sie nach Abschluss der Installation, ob Node.js korrekt installiert wurde.

1. Öffnen Sie Ihren Code-Editor
2. Öffnen Sie das integrierte Terminal

   * In VS Code können Sie es über das Menü öffnen: **Terminal → New Terminal**
3. Führen Sie den folgenden Befehl aus:

   ```bash
   node -v
   ```

Wenn Node.js korrekt installiert ist, sollte eine Versionsnummer auf dem Bildschirm angezeigt werden.

Sie können npm ebenfalls überprüfen, indem Sie Folgendes ausführen:

```bash
npm -v
```

## Wenn der Befehl nicht gefunden wird

Wenn Sie eine Meldung wie `command not found` oder `node is not recognized` sehen, bedeutet das in der Regel, dass Node.js nicht im PATH Ihres Systems verfügbar ist.

* Unter **Windows** hilft es oft, das Terminal zu schließen und erneut zu öffnen (oder den Computer neu zu starten, falls das nicht hilft)
* Unter **macOS** und **Linux** ist das bei Verwendung des offiziellen Installationsprogramms selten

Wenn das Problem weiterhin besteht, installieren Sie Node.js erneut mit dem offiziellen Installationsprogramm und stellen Sie sicher, dass Sie die Standardoptionen übernehmen.

{% callout type="note" title="Auf einem firmenverwalteten Rechner?" %}
Wenn keine der oben genannten Lösungen hilft, wurde Node.js möglicherweise aufgrund von IT-Einschränkungen gar nicht zum `PATH` Ihres Systems hinzugefügt. Wenden Sie sich an Ihre IT-Administration, um es hinzufügen zu lassen, oder fragen Sie nach, ob Node.js stattdessen über das Software-Center Ihres Unternehmens installiert werden sollte.
{% /callout %}

## Nächster Schritt

- [Git installieren](/de/prerequisites/git)
