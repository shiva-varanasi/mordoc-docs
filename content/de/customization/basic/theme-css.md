---
title: Theme CSS
description: Passen Sie die Farben Ihrer Mordoc-Website mit Theme CSS an.
---

Wenn Sie bereit sind, das Branding Ihres Unternehmens anzupassen, verwenden Sie `config/styles/theme.css`. Eine einzelne Farbänderung hier bringt Sie den größten Teil des Weges zu einer Website, die sich wie Ihre eigene anfühlt.

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

## Nächster Schritt

- [Eine Schriftfamilie festlegen](/de/customization/basic/font-family).
