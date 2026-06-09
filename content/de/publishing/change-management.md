---
title: Änderungsmanagement mit Git
description: Verwenden Sie Git und Plattformen wie GitHub oder GitLab, um Dokumentationsänderungen mit der gleichen Sorgfalt wie Quellcode zu verwalten.
---

Ihre Dokumentation besteht aus Dateien — Markdown-Seiten, YAML-Konfiguration, Bilder. Diese Dateien in einem Git-Repository zu pflegen verwandelt Ihr Dokumentationsprojekt in etwas wesentlich Leistungsfähigeres als einen gemeinsamen Ordner mit Textdateien.

Diese Seite erklärt, wie Sie Dokumentationsänderungen mit Git verwalten und warum der Docs-as-Code-Ansatz das möglich macht.

## Warum Git für Dokumentation geeignet ist

Software-Teams verwenden Git seit Jahrzehnten, weil es echte Probleme löst: nachverfolgen, wer was wann geändert hat, Änderungen vor der Veröffentlichung prüfen, Fehler rückgängig machen und teamübergreifend arbeiten, ohne sich gegenseitig zu überschreiben.

Dokumentation hat genau dieselben Probleme.

Wenn Ihre Dokumentation aus Markdown-Dateien unter Versionskontrolle besteht:

* Jede Änderung wird mit Autor, Zeitstempel und Grund festgehalten
* Prüfer sehen genau, was sich geändert hat, bevor etwas veröffentlicht wird
* Fehler lassen sich mit `git revert` rückgängig machen
* Mehrere Mitwirkende können parallel auf separaten Branches arbeiten

Das ist die Kernidee hinter Docs-as-Code: Dokumentation mit der gleichen technischen Sorgfalt behandeln wie Software.

## Der grundlegende Arbeitsablauf

Eine typische Dokumentationsänderung folgt diesem Muster:

1. Einen Branch für die Änderung erstellen
2. Seiten, Konfiguration oder Assets bearbeiten
3. Die Änderungen mit einer kurzen Beschreibung committen
4. Den Branch in das Remote-Repository pushen
5. Einen Pull Request oder Merge Request zur Überprüfung öffnen
6. Nach der Genehmigung in den Haupt-Branch mergen
7. Die aktualisierte Dokumentation bauen und deployen

## Einen Branch erstellen

Statt direkt auf dem Haupt-Branch zu arbeiten, erstellen Sie für jede Änderung einen Branch:

```bash
git checkout -b installationsanleitung-aktualisieren
```

Benennen Sie den Branch nach der Änderung. Namen wie `installationsanleitung-aktualisieren` oder `franzoesische-uebersetzung-hinzufuegen` zeigen Prüfern auf einen Blick, was sie erwartet.

Die Arbeit auf einem Branch hält Ihre Änderungen isoliert, bis sie bereit sind. Der Haupt-Branch bleibt stabil und spiegelt immer den aktuell veröffentlichten Stand wider.

## Änderungen committen

Sobald Sie Ihre Dateien bearbeitet haben, stagen und committen Sie sie:

```bash
git add .
git commit -m "Installationsschritte für Node 22 aktualisieren"
```

Schreiben Sie eine kurze, klare Nachricht, die beschreibt, was sich geändert hat und warum. Gute Commit-Nachrichten helfen Prüfern, die Absicht zu verstehen, und machen es einfach, eine Änderung Monate später nachzuvollziehen.

Für größere Änderungen verwenden Sie eine mehrzeilige Nachricht:

```bash
git commit -m "Authentifizierungsleitfaden überarbeiten

Alten Token-Ablauf durch neue OAuth2-Anleitung ersetzen.
Schließt Issue #48."
```

## Pushen und einen Pull Request öffnen

Pushen Sie den Branch in Ihr Remote-Repository:

```bash
git push origin installationsanleitung-aktualisieren
```

Öffnen Sie dann über die Web-Oberfläche der Plattform einen Pull Request auf GitHub oder einen Merge Request auf GitLab.

Ein Pull Request zeigt Prüfern einen genauen Diff — genau welche Zeilen hinzugefügt, geändert oder entfernt wurden. Prüfer können Inline-Kommentare hinterlassen, Überarbeitungen anfordern oder die Änderung genehmigen. Nichts wird gemergt, bis es bereit ist.

Dieser Überprüfungsschritt ist einer der deutlichsten Vorteile von Docs-as-Code. In einem Wiki oder einem gemeinsamen Dokument werden Änderungen sofort sichtbar. Mit einem Pull Request durchläuft jede Änderung eine Prüfung, bevor Leser sie sehen.

## Den Haupt-Branch schützen

Die meisten Git-Plattformen ermöglichen es, den Haupt-Branch zu schützen, sodass nicht direkt darauf gepusht werden kann. Änderungen können ihn nur durch einen geprüften und genehmigten Pull Request erreichen.

Das bedeutet, dass Ihre veröffentlichte Dokumentation immer in einem bekannt guten Zustand ist. Ein Tippfehler oder ein defekter Link auf einem ungeprüften Branch kann Leser nicht beeinflussen, bis ein Prüfer ihn entdeckt und die Korrektur genehmigt.

Richten Sie Branch-Schutzregeln so früh wie möglich ein. Es ist eine kleine Konfigurationsänderung mit erheblicher Auswirkung auf die Dokumentationsqualität.

## Mit einer Build- und Deploy-Pipeline verbinden

Sobald Änderungen in den Haupt-Branch gemergt werden, müssen Sie die Website noch bauen und deployen. Sie können dies manuell tun — `npm run build` ausführen und `dist/` hochladen — oder es mit einer CI/CD-Pipeline automatisieren.

Ein verbreitetes Setup:

* Bei jedem Pull Request: den Build ausführen, um sicherzustellen, dass der Inhalt fehlerfrei baut
* Bei jedem Merge in main: den Build ausführen und automatisch deployen

GitHub Actions, GitLab CI und ähnliche Tools unterstützen beide Schritte. Wenn die Pipeline eingerichtet ist, ist das Mergen eines Pull Requests der einzige manuelle Schritt, der zum Veröffentlichen einer Dokumentationsänderung erforderlich ist.

## Den Verlauf nutzen

Mit der Zeit wird Ihr Commit-Verlauf zu einer Aufzeichnung, wie die Dokumentation sich entwickelt hat. Sie können Fragen beantworten wie:

* Wann wurde diese Seite hinzugefügt, und von wem?
* Warum wurde dieser Konfigurationswert geändert?
* Welche Dokumentation wurde zusammen mit dem letzten Produktrelease ausgeliefert?

Klare Commit-Nachrichten und Branch-Namen machen diesen Verlauf nützlich statt nur dekorativ.

## Nächster Schritt

[Website bauen](/de/publishing/build-your-site).
