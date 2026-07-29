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

## Die Akzentfarbe ändern

Ersetzen Sie den Wert von `--accent` durch Ihre Markenfarbe:

```css
:root {
  --accent: #2563eb;
}
```

Speichern Sie die Datei. Wenn Ihr lokaler Server läuft, aktualisieren Sie den Browser, um die Änderung zu sehen.

## Eine andere Akzentfarbe für den Dunkelmodus festlegen

Wenn Ihre Markenfarbe auf einem dunklen Hintergrund nicht genug Kontrast bietet, überschreiben Sie `--accent` erneut innerhalb eines `.dark`-Selektors:

```css
:root {
  --accent: #2563eb;
}

.dark {
  --accent: #60a5fa;
}
```

Mordoc fügt der Seite die `dark`-Klasse hinzu, wenn der Leser zum Dunkelmodus wechselt, sodass dieser zweite Wert nur dort gilt. Der `:root`-Wert deckt den Hellmodus wie zuvor ab.

## Wie sich die Akzentfarbe über die Website verteilt

`--accent` ist die eine Farbe, die Mordoc Sie festzulegen bittet. Jeder andere Akzentfarbton auf der Website, etwa der hellere Farbton hinter einem aktiven Navigationselement oder der dunklere Farbton, den eine Schaltfläche beim Hover annimmt, wird automatisch aus diesem einen Wert berechnet.

Das bedeutet, eine Änderung von `--accent` aktualisiert Links, Schaltflächen, aktive Navigationszustände, Karten-Tags und ähnliche Details auf der gesamten Website gleichzeitig. Jeder Modus berechnet seine Farbtöne aus dem jeweils aktiven `--accent`-Wert für diesen Modus neu, sodass Hell- und Dunkelmodus konsistent bleiben, selbst wenn Sie für sie unterschiedliche Farben festgelegt haben. Sie müssen nicht jede einzelne Farbe manuell aufspüren und festlegen.

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
