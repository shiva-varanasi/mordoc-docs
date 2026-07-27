---
title: Sequenzdiagramme
description: Zeigen Sie Nachrichten, die im Zeitverlauf zwischen Teilnehmern ausgetauscht werden, mit einer Klartext-Syntax und optionalen Icons pro Akteur.
---

Ein Sequenzdiagramm zeigt Teilnehmer ("Akteure") als Spalten und Nachrichten zwischen ihnen als Pfeile, die die Seite hinunter in der Reihenfolge verlaufen, in der sie auftreten. Verwenden Sie es für Anfrage-/Antwort-Abläufe, Protokoll-Durchgänge oder — wie im Beispiel unten — jede Geschichte, bei der die Reihenfolge der Ereignisse eine Rolle spielt.

## Grundlegende Syntax

Schreiben Sie das Diagramm innerhalb eines ` ```sequence-diagram `-eingezäunten Codeblocks:

````markdown
```sequence-diagram
actor alice as "Alice"
actor bob as "Bob"

alice -> bob: Hallo
bob --> alice: Hallo zurück
```
````

Zwei Arten von Zeilen bilden die Syntax: **Akteur-Deklarationen** und **Nachrichten**.

## Akteure deklarieren

```markdown
actor <id> [as "<label>"] [icon=<path>]
```

* `<id>` ist, wie Sie sich in Nachrichten auf diesen Akteur beziehen. Es muss mit einem Buchstaben oder Unterstrich beginnen.
* `as "<label>"` legt den Text fest, der unter der Spalte des Akteurs angezeigt wird. Ohne diese Angabe wird die `<id>` selbst angezeigt.
* `icon=<path>` zeigt ein kleines Icon über der Beschriftung des Akteurs — siehe [Icons hinzufügen](#icons-hinzufügen).

Das Deklarieren von Akteuren im Voraus ist optional. Ein Akteur, der in einer Nachricht erwähnt wird, ohne zuvor deklariert worden zu sein, wird automatisch hinzugefügt, mit seiner id als Beschriftung und ohne Icon. Deklarieren Sie Akteure explizit, wenn Sie eine Beschriftung oder ein Icon möchten; für ein schnelles Diagramm, bei dem die reinen ids gut lesbar sind, können Sie die Deklarationen ganz weglassen.

Akteure erscheinen von links nach rechts in der Reihenfolge, in der sie zuerst auftauchen — sei es durch eine `actor`-Zeile oder ihr erstes Auftreten in einer Nachricht.

## Nachrichten senden

```markdown
<from> -> <to>: <message text>
<from> --> <to>: <message text>
```

Jede Nachricht wird zu einem nummerierten Pfeil zwischen den Spalten zweier Akteure, in der Reihenfolge, in der die Nachrichten im eingezäunten Block erscheinen. Mordoc nummeriert sie für Sie — Sie schreiben die Nummer nie selbst.

### Durchgezogene vs. gestrichelte Pfeile

Verwenden Sie `->` für einen durchgezogenen Pfeil und `-->` für einen gestrichelten. Keiner hat eine verbindliche Bedeutung, aber die gängige Konvention — und die im Beispiel unten verwendete — ist ein durchgezogener Pfeil für einen Aufruf und ein gestrichelter Pfeil für dessen Antwort:

```markdown
frodo -> aragorn: Wirst du mir helfen?
aragorn --> frodo: Du hast mein Schwert
```

Wenn eine Abfolge von Nachrichten einen Akteur "beschäftigt" hält — er ist das `from` oder `to` einer Reihe aufeinanderfolgender Nachrichten — zeichnet Mordoc automatisch einen farbigen Aktivierungsbalken entlang dieses Abschnitts seiner Lebenslinie. Sie konfigurieren das nicht; es ergibt sich aus den Nachrichten, die Sie schreiben.

### Selbstnachrichten

Ein Akteur kann sich selbst eine Nachricht senden:

```markdown
frodo -> frodo: Halte es sicher,\nhalte es geheim
```

Dies wird als kleine Schleife dargestellt, die von der eigenen Lebenslinie des Akteurs ausgeht und zu ihr zurückkehrt, anstatt als Linie zu einer anderen Spalte.

### Mehrzeilige Beschriftungen

Eine Beschriftung bricht überall dort auf mehrere Zeilen um, wo Sie ein literales `\n` setzen:

```markdown
gandalf -> frodo: Der Ring muss vernichtet werden\nin den Feuern des Schicksalsbergs
```

Mordoc bricht eine Beschriftung nie automatisch um — wenn eine Beschriftung zu lang wird, fügen Sie Ihr eigenes `\n` dort ein, wo sie umbrechen soll.

### Kommentare

Eine Zeile, die mit `#` beginnt, wird ignoriert — nützlich, um Abschnitte eines längeren Diagramms zu beschriften:

```markdown
# Der Rat von Elrond
gandalf -> frodo: Der Ring muss vernichtet werden
```

## Icons hinzufügen

Setzen Sie `icon=<path>` bei einem Akteur, um ein kleines Bild über seiner Beschriftung anzuzeigen, anstatt nur Text:

```markdown
actor frodo as "Frodo" icon=/icons/frodo.svg
```

Der Pfad funktioniert genau wie ein Bild-`src` — legen Sie die Datei unter `public/` ab und referenzieren Sie sie mit einem Pfad, der bei `/` beginnt. Mordoc liefert kein gebündeltes Icon-Set mit, bringen Sie also Ihre eigenen SVGs mit; ein einfaches quadratisches Icon von etwa 40×40px liest sich am besten.

{% callout type="tip" title="Icons einfach halten" %}
Icons werden klein gerendert, neben mehreren anderen in der Kopfzeile des Diagramms. Eine flache Silhouette oder eine einzelne kräftige Form auf einem einfarbigen Hintergrund bleibt bei dieser Größe gut lesbar — feine Linienzeichnungen neigen dazu, zu verschwinden.
{% /callout %}

## Beispiel: Der Rat von Elrond

Hier ist ein vollständiges Diagramm, das Icons, Kommentare, beide Pfeilstile, eine Selbstnachricht und mehrzeilige Beschriftungen gemeinsam verwendet — alles innerhalb einer einzigen Szene:

````markdown
```sequence-diagram
# Der Rat von Elrond
actor gandalf as "Gandalf" icon=/icons/sequence-diagrams/gandalf.svg
actor frodo as "Frodo" icon=/icons/sequence-diagrams/frodo.svg
actor aragorn as "Aragorn" icon=/icons/sequence-diagrams/aragorn.svg
actor sauron as "Sauron" icon=/icons/sequence-diagrams/sauron.svg

gandalf -> frodo: Der Ring muss vernichtet werden\nin den Feuern des Schicksalsbergs
frodo -> gandalf: Ich werde ihn nehmen, obwohl\nich den Weg nicht kenne
sauron -> frodo: Ich sehe dich
frodo -> aragorn: Wirst du mir helfen,\nden Ring zu beschützen?
aragorn --> frodo: Du hast mein Schwert
frodo -> frodo: Halte es sicher,\nhalte es geheim
```
````

Und so sieht das gerendert aus:

```sequence-diagram
# Der Rat von Elrond
actor gandalf as "Gandalf" icon=/icons/sequence-diagrams/gandalf.svg
actor frodo as "Frodo" icon=/icons/sequence-diagrams/frodo.svg
actor aragorn as "Aragorn" icon=/icons/sequence-diagrams/aragorn.svg
actor sauron as "Sauron" icon=/icons/sequence-diagrams/sauron.svg

gandalf -> frodo: Der Ring muss vernichtet werden\nin den Feuern des Schicksalsbergs
frodo -> gandalf: Ich werde ihn nehmen, obwohl\nich den Weg nicht kenne
sauron -> frodo: Ich sehe dich
frodo -> aragorn: Wirst du mir helfen,\nden Ring zu beschützen?
aragorn --> frodo: Du hast mein Schwert
frodo -> frodo: Halte es sicher,\nhalte es geheim
```

Ein paar Dinge, die auffallen:

* **Gandalf** ist nur für den einleitenden Austausch aktiv, und **Sauron** nur für seine einzige, beunruhigende Zeile — jeder erhält einen kurzen Aktivierungsbalken.
* **Frodo** ist an jeder Nachricht beteiligt, sodass seine Lebenslinie den ganzen Weg über aktiv bleibt — einschließlich seiner abschließenden Selbstnachricht.
* Die vier `actor`-Zeilen werden vor jeder Nachricht deklariert, weshalb sie in dieser Reihenfolge von links nach rechts erscheinen — `gandalf`, `frodo`, `aragorn`, `sauron` — statt in der Reihenfolge, in der sie zuerst angesprochen werden.
* Klicken Sie auf das Diagramm, um es mit Zoom-Steuerung im Vollbild zu öffnen, genau wie bei einem Inhaltsbild.

## Nächste Schritte

* [Konfigurieren Sie Ihre Website](/de/configuration/site-configuration).
