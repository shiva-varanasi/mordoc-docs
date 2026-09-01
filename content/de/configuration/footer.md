---
title: Footer
description: Konfigurieren Sie die Spalten aus Links und Text, die am unteren Rand jeder Seite angezeigt werden.
---

Jede Mordoc-Website hat einen Footer. Ohne jede Konfiguration zeigt er eine einzelne Zeile „Powered by Mordoc“. Sie können diese durch eigene Spalten aus Links und Text ersetzen.

## Die Footer-Datei erstellen

Der Footer lebt in dieser optionalen Datei:

```text
config/navigation/footer.yaml
```

Erstellen Sie die Datei nur, wenn Sie den Standard-Footer ersetzen möchten.

## Footer-Spalten hinzufügen

Der Footer hat drei benannte Spalten: `start`, `center` und `end`, die in dieser Reihenfolge von links nach rechts angezeigt werden. Alle drei sind optional:

```yaml
start:
  - "[Privacy policy](/privacy)"
  - Powered by [Mordoc](https://mordoc.dev)
center:
  - "[Support](/support)"
end:
  - "© 2026 Acme Inc."
```

Jede Spalte ist eine Liste von Zeilen, von oben nach unten gestapelt. Eine Zeile ist reiner Text, reiner Text mit einem Link, oder eine Mischung aus beidem.

## Einen Link innerhalb einer Zeile hinzufügen

Verwenden Sie die Markdown-typische Link-Syntax an beliebiger Stelle in einer Zeile:

```yaml
- "[Privacy policy](/privacy)"
```

Alles außerhalb der eckigen Klammern wird als reiner Text dargestellt; der Teil in Klammern wird zu einem Link. Externe Links (die mit `http://`, `https://` oder `//` beginnen) öffnen sich in einem neuen Tab; alles andere wird als Route auf Ihrer eigenen Website behandelt.

{% callout type="warning" title="Zeilen, die mit einem Link beginnen, in Anführungszeichen setzen" %}
Eine Zeile, die mit einer nicht in Anführungszeichen gesetzten `[` beginnt, wird von YAML als Beginn einer Liste gelesen, nicht als Text:

```yaml
# Wrong — YAML sees a list, not a footer line
- [Privacy policy](/privacy)

# Right — quoted, so YAML reads it as one string
- "[Privacy policy](/privacy)"
```
{% /callout %}

## Den Footer ausschalten

Fügen Sie die Datei ohne Zonen oder mit ausschließlich leeren Zonen hinzu, und Mordoc rendert überhaupt keinen Footer. Das unterscheidet sich davon, die Datei ganz wegzulassen, was auf die Standardzeile „Powered by Mordoc“ zurückfällt:

## Footer-Zeilen übersetzen

Footer-Zeilen werden auf dieselbe Weise übersetzt wie Navigations-Labels, in `config/navigation/translations/<lang>.yaml`. Siehe [Navigationsübersetzungen](/de/configuration/navigation-translations) für die vollständige Syntax, einschließlich wie interne Links innerhalb einer Footer-Zeile ihren Pfad für jede Sprache von Hand vorangestellt bekommen müssen.

## Speichern und den Footer überprüfen

Speichern Sie `config/navigation/footer.yaml`.

Wenn Ihr lokaler Server läuft, scrollen Sie auf einer beliebigen Seite nach unten, um die Änderung zu sehen.

## Nächster Schritt

[Sprachen konfigurieren](/de/configuration/languages).
