---
title: Callouts
description: Heben Sie Hinweise, Tipps, Warnungen und wichtige Meldungen auf Mordoc-Seiten hervor.
---

Callouts helfen dabei, wichtige Informationen vom Rest der Seite abzuheben.

Verwenden Sie sie, wenn ein Leser innehalten, etwas bemerken oder vorsichtig sein sollte, bevor er weiterliest. Verwenden Sie keinen Callout für jeden wichtigen Satz; zu viele Callouts machen eine Seite schwerer zu überfliegen.

## Einen einfachen Callout hinzufügen

Ein Callout beginnt mit `{% callout %}` und endet mit `{% /callout %}`.

```markdown
{% callout type="note" title="Gut zu wissen" %}
Sie können die lokale Vorschau geöffnet lassen, während Sie Seiten bearbeiten.
{% /callout %}
```

Der Text zwischen den öffnenden und schließenden Tags ist der Callout-Inhalt.

## Einen Typ wählen

Mordoc unterstützt vier Callout-Typen:

* `note` für nützlichen zusätzlichen Kontext
* `tip` für hilfreiche Vorschläge
* `warning` für Dinge, bei denen Leser vorsichtig sein sollten
* `danger` für ernste oder riskante Situationen

Der `type`-Wert ist optional. Wenn Sie ihn weglassen, verwendet Mordoc `note`.

Der `title`-Wert ist ebenfalls optional. Fügen Sie ihn hinzu, wenn er Lesern hilft, den Callout schnell zu verstehen.

## Note

Verwenden Sie `note` für hilfreiche Informationen, die den Haupttext unterstützen.

```markdown
{% callout type="note" title="Gut zu wissen" %}
Mordoc aktualisiert die lokale Vorschau, wenn Sie Inhaltsänderungen speichern.
{% /callout %}
```

## Tip

Verwenden Sie `tip` für Ratschläge, die eine Aufgabe einfacher machen.

```markdown
{% callout type="tip" title="Schreibtipp" %}
Halten Sie Seitentitel kurz, damit sie in der Navigation leichter zu überfliegen sind.
{% /callout %}
```

## Warning

Verwenden Sie `warning`, wenn Leser etwas verlangsamen oder überprüfen sollten, bevor sie fortfahren.

```markdown
{% callout type="warning" title="Pfad überprüfen" %}
Verwenden Sie Seitenadressen wie `/guides/install`, nicht Markdown-Dateipfade wie `./install.md`.
{% /callout %}
```

## Danger

Verwenden Sie `danger` nur für ernste Situationen.

```markdown
{% callout type="danger" title="Generierte Dateien nicht bearbeiten" %}
Bearbeiten Sie keine Dateien in `dist/`. Mordoc erstellt diesen Ordner beim Bauen der Website neu.
{% /callout %}
```

## Titel sind optional

Sie können einen Callout ohne Titel schreiben:

```markdown
{% callout type="note" %}
Dieser Callout hat keinen Titel.
{% /callout %}
```

Verwenden Sie einen Titel, wenn er dem Leser hilft, die Nachricht schnell zu verstehen.

## Callouts kurz halten

Ein guter Callout ist in der Regel ein kurzer Absatz oder eine kleine Liste. Wenn der Callout zu lang wird, muss er möglicherweise ein normaler Abschnitt werden.

## Nächster Schritt

[Tabellen erstellen](/de/writing-content/tables).
