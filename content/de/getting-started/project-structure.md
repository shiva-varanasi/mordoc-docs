---
title: Projektstruktur
description: Erfahren Sie, was das Starter-Projekt enthält und welche Dateien Sie zuerst bearbeiten werden.
---

Ein Mordoc-Projekt ist nur ein Ordner auf Ihrem Computer. Darin befinden sich einige Dateien für Ihre Dokumentationsinhalte, einige für die Website-Einstellungen und einige, die automatisch erstellt werden, damit Mordoc laufen kann.

Sie müssen nicht alles auf einmal verstehen. Diese Seite ist nur eine erste Übersicht des Projekts, das Sie mit `create-mordoc-app` erstellt haben.

## Der erstellte Ordner

Wenn Sie Folgendes ausgeführt haben:

```bash
npx create-mordoc-app my-docs
```

Haben Sie jetzt einen Ordner namens `my-docs`.

Darin sehen Sie etwa Folgendes:

```text
my-docs/
├── .gitignore
├── package.json
├── content/
│   └── en/
│       ├── index.md
│       ├── lore.md
│       ├── safeguards.md
│       └── wielding-the-ring.md
├── config/
│   ├── site.json
│   ├── navigation/
│   │   └── sidenav.yaml
│   ├── assets/
│   │   ├── logo.svg
│   │   └── logo-dark.svg
│   └── styles/
│       └── theme.css
├── public/
│   └── images/
│       ├── ring-og.svg
│       └── icons/
│           ├── book.svg
│           ├── shield.svg
│           └── spark.svg
├── node_modules/
└── package-lock.json
```

Der Starter-Inhalt ist fiktiv, damit Sie eine funktionierende Dokumentationswebsite sehen können, bevor Sie sie mit Ihren eigenen Inhalten ersetzen.

## Die Dateien, die Sie am häufigsten bearbeiten werden

Der Großteil Ihrer Arbeit findet an drei Stellen statt:

* `content/` für die Seiten, die Leser lesen werden
* `config/` für Website-Einstellungen, Navigation, Branding und kleinere Anpassungen
* `public/` für Bilder und Dateien, die von Ihren Seiten verwendet werden

Die anderen generierten Dateien können Sie zunächst ignorieren. Sie werden später auf dieser Seite erklärt, damit Sie wissen, was sie sind, wenn Sie sie sehen.

## content

`content/` ist der Ort, an dem Ihre Dokumentationsseiten gespeichert sind.

Im Starter-Projekt sieht es so aus:

```text
content/
└── en/
    ├── index.md
    ├── lore.md
    ├── safeguards.md
    └── wielding-the-ring.md
```

Jede `.md`-Datei ist eine Markdown-Seite. Markdown ist das Klartextformat, das Sie für Überschriften, Absätze, Listen, Links, Bilder und Mordoc-Komponenten verwenden.

Der Ordner `en` bedeutet, dass dieser Inhalt auf Englisch verfasst ist. Wenn Ihre Website später mehrere Sprachen hat, kann jede Sprache ihren eigenen Ordner haben.

Die Starter-Seiten werden zu folgenden URLs auf der Dokumentationswebsite:

```text
content/en/index.md             -> /
content/en/lore.md              -> /lore
content/en/safeguards.md        -> /safeguards
content/en/wielding-the-ring.md -> /wielding-the-ring
```

Merken Sie sich zunächst Folgendes:

* Bearbeiten Sie Dateien in `content/en/`, wenn Sie Seitentext ändern möchten.
* Behalten Sie `content/en/index.md`; es ist die Startseite der Starter-Website.
* Ersetzen Sie die fiktiven Beispielseiten durch Ihre eigene Dokumentation, wenn Sie bereit sind.

Später wird der Abschnitt [Inhalte schreiben](/de/writing-content/markdown-basics) Markdown, Frontmatter, Links, Bilder und die Mordoc-Syntax im Detail erklären.

## config

`config/` ist der Ort, an dem Sie Mordoc mitteilen, wie sich Ihre Dokumentationswebsite verhalten soll.

Im Starter-Projekt sieht es so aus:

```text
config/
├── site.json
├── navigation/
│   └── sidenav.yaml
├── assets/
│   ├── logo.svg
│   └── logo-dark.svg
└── styles/
    └── theme.css
```

Sie müssen das nicht alles sofort bearbeiten. Das Starter-Projekt funktioniert bereits. Betrachten Sie diesen Ordner als den Ort, zu dem Sie zurückkehren, wenn Sie die Website umbenennen, die Navigation ändern, das Logo ersetzen oder das Theme anpassen möchten.

### site.json

`config/site.json` speichert grundlegende Informationen über die Website.

Die Starter-Datei sieht so aus:

```json
{
  "name": "The Ring of Power",
  "description": "A field guide for keepers, scholars, and reluctant bearers of the One Ring.",
  "baseUrl": "https://ring-of-power.example.com",
  "defaultLanguage": "en"
}
```

Sie werden irgendwann den Namen, die Beschreibung und die Produktions-URL für Ihre eigene Dokumentationswebsite ändern.

Das müssen Sie noch nicht tun. Sie werden jedes Feld im Detail auf der Seite [Website-Konfiguration](/de/configuration/site-configuration) durchgehen.

### navigation

`config/navigation/sidenav.yaml` steuert die Seitenleisten-Links.

Die Starter-Navigation sieht so aus:

```yaml
- label: The Ring
  expanded: true
  children:
    - label: Lore of the Ring
      path: /lore
    - label: Wielding the Ring
      path: /wielding-the-ring
    - label: Safeguards
      path: /safeguards
```

Beachten Sie zunächst, dass jeder sichtbare Link zwei Teile hat:

* `label` ist der Text, den Leser in der Seitenleiste sehen.
* `path` ist die Seiten-URL.

Wenn Sie eigene Seiten hinzufügen, aktualisieren Sie diese Datei, damit Leser sie finden können. Sie werden diesen Schritt auf der Seite [Navigationsgrundlagen](/de/getting-started/navigation-basics) durchgehen.

### assets

`config/assets/` ist für Website-weite Bilder wie das Logo.

Das Starter-Projekt enthält:

```text
config/assets/
├── logo.svg
└── logo-dark.svg
```

Diese können Sie zunächst in Ruhe lassen. Später können Sie sie durch Ihre eigenen Logo-Dateien ersetzen.

Mehr dazu unter [Bilder und Dateien](/de/getting-started/images-and-files).

### styles

`config/styles/theme.css` ist für kleine visuelle Änderungen, wie zum Beispiel Theme-Farben.

Sie müssen diese Datei beim Erlernen der Grundlagen nicht bearbeiten. Mordoc liefert Ihnen bereits ein funktionierendes Design.

Später wird [Theme CSS](/de/customization/basic/theme-css) erklären, was sicher angepasst werden kann.

## public

`public/` ist für Bilder und Dateien, die in Ihren Dokumentationsseiten verwendet werden.

Das Starter-Projekt enthält Icons und ein Bild, das von den Beispielseiten verwendet wird:

```text
public/
└── images/
    ├── ring-og.svg
    └── icons/
        ├── book.svg
        ├── shield.svg
        └── spark.svg
```

Wenn sich eine Datei in `public/` befindet, können Sie sie von einer Seite aus mit einem Pfad referenzieren, der mit `/` beginnt.

Zum Beispiel:

```markdown
![Diagramm](/images/diagram.png)
```

Sie müssen noch keine Bilder hinzufügen. Dies wird später unter [Bilder und Dateien](/de/getting-started/images-and-files) behandelt.

## package.json

`package.json` ist eine kleine Projektinformationsdatei.

Sie werden sie nicht oft bearbeiten, aber es ist nützlich zu wissen, was sie tut. Sie speichert:

* Den Projektnamen
* Die Befehle, die Sie ausführen, wie `npm run dev` und `npm run build`
* Die Mordoc-Version, die Ihr Projekt verwendet

Ein vereinfachtes Beispiel sieht so aus:

```json
{
  "name": "my-docs",
  "private": true,
  "scripts": {
    "dev": "mordoc dev",
    "build": "mordoc build"
  },
  "devDependencies": {
    "mordoc": "^1.3.0"
  }
}
```

Sie haben bereits einen Befehl aus dieser Datei verwendet:

```bash
npm run dev
```

Wenn Sie später auf eine neuere Mordoc-Version aktualisieren möchten, kommen Sie möglicherweise zu dieser Datei zurück. Für jetzt können Sie sie so lassen, wie sie ist.

## Dateien, die Sie nicht bearbeiten müssen

Einige Dateien und Ordner werden automatisch erstellt. Es ist normal, sie zu sehen, aber Sie müssen sie in der Regel nicht öffnen oder bearbeiten.

### node_modules

`node_modules/` enthält installierte Pakete, die Mordoc zum Ausführen benötigt.

Sie müssen nichts innerhalb von `node_modules/` bearbeiten. Falls er jemals fehlt, kann er durch Ausführen von `npm install` neu erstellt werden.

### package-lock.json

`package-lock.json` wird von npm erstellt. Es hilft npm, dieselben Paketversionen konsistent zu installieren.

Sie müssen es nicht manuell bearbeiten.

### .gitignore

`.gitignore` teilt Git mit, welche generierten Ordner nicht in der Versionshistorie gespeichert werden sollen.

Sie können es in Ruhe lassen.

### dist

`dist/` wird später erstellt, wenn Sie die Website bauen:

```bash
npm run build
```

`dist/` enthält die fertigen Website-Dateien zur Veröffentlichung.

Bearbeiten Sie Dateien in `dist/` nicht manuell. Wenn Sie die Website ändern müssen, bearbeiten Sie die Quelldateien in `content/`, `config/` oder `public/` und bauen Sie dann erneut.

Mehr darüber erfahren Sie später unter [Website bauen](/de/publishing/build-your-site).

## Nächster Schritt

- [Ihre ersten Seiten schreiben](/de/getting-started/write-pages).