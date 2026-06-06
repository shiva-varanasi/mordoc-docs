---
title: Ein Projekt erstellen
description: Erstellen Sie ein neues Mordoc-Dokumentationsprojekt aus der Starter-Vorlage.
---

Ein Mordoc-Projekt ist ein Ordner, der Ihre Markdown-Inhalte, Konfigurationsdateien und statische Assets enthält. Mordoc kümmert sich um das Verhalten der Dokumentationswebsite, sodass Sie sich auf das Schreiben und Organisieren von Inhalten konzentrieren können.

Der schnellste Einstieg erfolgt mit `create-mordoc-app`. Es erstellt den Projektordner, kopiert eine Starter-Vorlage, fügt die erforderlichen Skripte hinzu und installiert Mordoc für Sie.

## Das Projekt erstellen

Öffnen Sie das Terminal in Ihrem Code-Editor und navigieren Sie zu dem Ordner, in dem Sie Ihre Dokumentationsprojekte ablegen möchten.

Führen Sie diesen Befehl aus:

```bash
npx create-mordoc-app my-docs
```

Ersetzen Sie `my-docs` durch den gewünschten Namen für Ihren Dokumentationsordner.

Der Befehl kann etwas Zeit in Anspruch nehmen. Er erstellt den Ordner, fügt die Starter-Dateien hinzu und bereitet das Projekt so vor, dass Sie es ausführen können.

{% callout type="note" title="Was ist npx?" %}
`npx` ist in npm enthalten. Es lädt `create-mordoc-app` herunter und führt es aus, ohne dass Sie es zuerst global installieren müssen.
{% /callout %}

## Auf die Erfolgsmeldung warten

Wenn der Befehl abgeschlossen ist, sollten Sie eine Erfolgsmeldung im Terminal sehen.

Wenn Sie eine Fehlermeldung sehen, lesen Sie sie sorgfältig. Häufige Ursachen sind:

* Der Ordnername existiert bereits
* Ihre Internetverbindung ist nicht verfügbar
* Node.js oder npm ist nicht korrekt installiert

Wenn der Befehl erfolgreich war, ist Ihr neues Dokumentationsprojekt bereit.

## In das Projekt wechseln

Wechseln Sie nach Abschluss des Befehls in den neuen Ordner:

```bash
cd my-docs
```

Wenn Sie einen anderen Projektnamen verwendet haben, verwenden Sie stattdessen diesen Ordnernamen.

## Den Ordner öffnen

Öffnen Sie den neuen Projektordner in Ihrem Code-Editor. Sie müssen noch nicht jede Datei verstehen. Im nächsten Schritt werden Sie die Website einfach ausführen und im Browser ansehen.

## Nächster Schritt

[Website lokal ausführen](/de/getting-started/run-locally).
