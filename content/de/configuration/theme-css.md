---
title: Theme CSS
description: Passen Sie Farben, Schriften und andere visuelle Einstellungen Ihrer Mordoc-Website mit Theme CSS an.
---

Mordoc liefert Ihnen standardmäßig ein funktionierendes Design.

Sie müssen kein CSS schreiben, um Seiten zu erstellen, Navigation hinzuzufügen oder Dokumentation zu veröffentlichen. Wenn Sie bereit sind, das Branding Ihres Unternehmens anzupassen, verwenden Sie `config/styles/theme.css`.

## Die Theme-Datei öffnen

Das Theme-CSS befindet sich hier:

```text
config/styles/theme.css
```

Das Starter-Projekt enthält diese Datei. Im Ring of Power-Beispiel sieht sie so aus:

```css
:root {
  --accent: #D64518;
}
```

Mordoc lädt diese Datei automatisch. Sie müssen sie nicht an anderer Stelle importieren.

## Die Akzentfarbe ändern

Die häufigste Theme-Änderung ist die Akzentfarbe.

Ersetzen Sie den Wert von `--accent` durch Ihre Markenfarbe:

```css
:root {
  --accent: #2563eb;
}
```

Mordoc verwendet `--accent` auf der gesamten Website für Links, aktive Navigationszustände, Schaltflächen und andere Hervorhebungen.

Sie müssen nicht jede verwandte Farbe manuell festlegen. Mordoc leitet hellere und dunklere Akzentfarbtöne aus `--accent` für Sie ab.

Speichern Sie die Datei. Wenn Ihr lokaler Server läuft, aktualisieren Sie den Browser, um die Änderung zu sehen.

## Wie Theme CSS funktioniert

Mordoc verwendet CSS-Variablen für sein Design.

Ihre Theme-Datei überschreibt diese Variablen in `:root`:

```css
:root {
  --accent: #2563eb;
  --font-sans: 'Inter', system-ui, sans-serif;
}
```

Für den Dunkelmodus verwenden Sie den `.dark`-Selektor:

```css
.dark {
  --color-bg: #121212;
  --color-fg: #e2e8f0;
}
```

Mordoc fügt die `dark`-Klasse zur Seite hinzu, wenn der Leser zum Dunkelmodus wechselt.

## Häufige globale Einstellungen

Diese Variablen sind ein guter Ausgangspunkt für leichte Branding-Änderungen:

* `--accent` für Links, Schaltflächen, aktive Navigation und andere Hervorhebungen
* `--color-bg` für den Hauptseitenhintergrund
* `--color-surface` für subtile Hintergrundbereiche, wie Blockzitate
* `--color-border` für Rahmen und Trennlinien
* `--color-fg` für die Haupttextfarbe
* `--color-content-fg` für Fließtext in Dokumentationsseiten
* `--color-fg-muted` für sekundären Text, wie Beschreibungen
* `--font-sans` für die Hauptwebsite-Schrift
* `--font-mono` für Inline-Code und Code-Blöcke
* `--content-max-width` für die maximale Breite des Seiteninhalts
* `--page-gutter` für horizontellen Abstand auf Landing-Pages

Beginnen Sie mit `--accent`. Fügen Sie weitere Variablen nur hinzu, wenn Sie eine feinere Kontrolle benötigen.

## Erweiterte Komponenteneinstellungen

Mordoc definiert auch Variablen für bestimmte Teile der Website, wie die Seitenleiste, den Header und Callouts.

Zum Beispiel:

* `--sidenav-bg` und `--sidenav-fg` für die Seitenleiste
* `--callout-note-accent` und ähnliche Variablen für Callout-Farben

Sie können diese in `config/styles/theme.css` überschreiben, wenn Sie eine tiefere Anpassung benötigen.

Für die meisten Unternehmensdokumentationswebsites sind die obigen globalen Einstellungen ausreichend.

## Zuerst Inhaltseinstellungen bevorzugen

Bevor Sie CSS ändern, prüfen Sie, ob die Seite oder Komponente bereits die Option hat, die Sie benötigen.

Zum Beispiel:

* Landing-Pages können Hero-Farben und -Hintergründe festlegen.
* Karten können Icons und Bilder verwenden.
* Callouts haben bereits eingebaute Typen.

Verwenden Sie Theme CSS, wenn Sie website-weite visuelle Änderungen vornehmen möchten, nicht wenn Sie versuchen, eine einzelne Seite anders zu gestalten.

## Die Datei klein halten

Fügen Sie nur Regeln hinzu, die Sie verstehen.

Eine kurze Theme-Datei ist einfacher zu pflegen, wenn Sie Mordoc aktualisieren oder das Branding später ändern.

## Generierte Dateien nicht bearbeiten

Theme-Änderungen gehören in:

```text
config/styles/theme.css
```

Bearbeiten Sie keine CSS-Dateien in `dist/`. Der `dist/`-Ordner wird beim Bauen der Website generiert, und Mordoc kann ihn beim nächsten Build ersetzen.

## Nächster Schritt

[Änderungsmanagement mit Git](/de/publishing/change-management).
