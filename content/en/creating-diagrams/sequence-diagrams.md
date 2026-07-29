---
title: Sequence Diagrams
description: Show messages passing between participants over time, with a plain-text syntax and optional per-actor icons.
---

A sequence diagram shows participants ("actors") as columns, and messages between them as arrows down the page in the order they happen. Use it for request/response flows, protocol walkthroughs, or any story where the order events happen in matters, like the example below.

## Basic syntax

Write the diagram inside a ` ```sequence-diagram ` fenced code block:

````markdown
```sequence-diagram
actor alice as "Alice"
actor bob as "Bob"

alice -> bob: Hello
bob --> alice: Hi there
```
````

Two kinds of lines make up the syntax: **actor declarations** and **messages**.

## Declaring actors

```markdown
actor <id> [as "<label>"] [icon=<path>]
```

* `<id>` is how you refer to this actor in messages. It must start with a letter or underscore.
* `as "<label>"` sets the text shown under the actor's column. Without it, the `<id>` itself is shown.
* `icon=<path>` shows a small icon above the actor's label. See [Adding icons](#adding-icons).

Declaring actors up front is optional. An actor mentioned in a message that was never declared is added automatically, using its id as its label and no icon. Declare actors explicitly whenever you want a label or icon; for a quick diagram where the raw ids read fine, you can skip declarations entirely.

Actors appear left to right in the order they're first seen, which is either an `actor` line or their first appearance in a message.

## Sending messages

```markdown
<from> -> <to>: <message text>    (solid arrow)
<from> --> <to>: <message text>   (dashed arrow)
```

Each message becomes a numbered arrow between two actors' columns, in the order the messages appear in the fenced block. Mordoc numbers them for you. You never write the number yourself.

### Solid vs. dashed arrows

Use `->` for a solid arrow and `-->` for a dashed one. Neither has enforced meaning. The common convention, also used in the example below, is a solid arrow for a call and a dashed arrow for its response:

```markdown
frodo -> aragorn: Will you help me?
aragorn --> frodo: You have my sword
```

An actor counts as "busy" whenever it's the `from` or `to` of a run of consecutive messages. Mordoc then draws a colored activation bar down that stretch of its lifeline automatically. You don't configure this; it falls out of the messages you write.

### Self-messages

An actor can send a message to itself:

```markdown
frodo -> frodo: Keep it safe,\nkeep it secret
```

This renders as a small loop out from and back to the actor's own lifeline, rather than a line to another column.

### Multi-line labels

A label wraps onto multiple lines wherever you put a literal `\n`:

```markdown
gandalf -> frodo: The Ring must be destroyed\nin the fires of Mount Doom
```

Mordoc never wraps a label automatically, so if a label runs long, add your own `\n` where you'd like it to break.

### Comments

A line starting with `#` is ignored, useful for labeling sections of a longer diagram:

```markdown
# The Council of Elrond
gandalf -> frodo: The Ring must be destroyed
```

## Adding icons

Set `icon=<path>` on an actor to show a small image above its label instead of just text:

```markdown
actor frodo as "Frodo" icon=/icons/frodo.svg
```

The path works exactly like an image `src`. Put the file under `public/` and reference it with a path starting at `/`. Mordoc doesn't ship a bundled icon set, so bring your own SVGs; a simple square icon around 40×40px reads best.

{% callout type="tip" title="Keep icons simple" %}
Icons render small, next to several others across the diagram's header row. A flat silhouette or a single bold shape on a solid background stays legible at that size, while fine linework tends to disappear.
{% /callout %}

## Example: The Council of Elrond

Here's a complete diagram that brings icons, comments, both arrow styles, a self-message, and multi-line labels together within a single scene:

````markdown
```sequence-diagram
# The Council of Elrond
actor gandalf as "Gandalf" icon=/icons/sequence-diagrams/gandalf.svg
actor frodo as "Frodo" icon=/icons/sequence-diagrams/frodo.svg
actor aragorn as "Aragorn" icon=/icons/sequence-diagrams/aragorn.svg
actor sauron as "Sauron" icon=/icons/sequence-diagrams/sauron.svg

gandalf -> frodo: The Ring must be destroyed\nin the fires of Mount Doom
frodo -> gandalf: I will take it, though\nI do not know the way
sauron -> frodo: I see you
frodo -> aragorn: Will you help me\nprotect the Ring?
aragorn --> frodo: You have my sword
frodo -> frodo: Keep it safe,\nkeep it secret
```
````

And here's what that renders as:

```sequence-diagram
# The Council of Elrond
actor gandalf as "Gandalf" icon=/icons/sequence-diagrams/gandalf.svg
actor frodo as "Frodo" icon=/icons/sequence-diagrams/frodo.svg
actor aragorn as "Aragorn" icon=/icons/sequence-diagrams/aragorn.svg
actor sauron as "Sauron" icon=/icons/sequence-diagrams/sauron.svg

gandalf -> frodo: The Ring must be destroyed\nin the fires of Mount Doom
frodo -> gandalf: I will take it, though\nI do not know the way
sauron -> frodo: I see you
frodo -> aragorn: Will you help me\nprotect the Ring?
aragorn --> frodo: You have my sword
frodo -> frodo: Keep it safe,\nkeep it secret
```

A few things to notice:

* **Gandalf** is only active for the opening exchange, and **Sauron** only for his single, unsettling line. Each gets a short activation bar.
* **Frodo** is involved in every message, so his lifeline stays active the whole way down. That includes his own closing self-message.
* The four `actor` lines are declared before any message, which is why they appear left to right in that order (`gandalf`, `frodo`, `aragorn`, `sauron`) rather than the order they're first spoken to.
* Click the diagram to open it full-screen with zoom controls, the same as a content image.

## Next steps

* [Configure your site](/configuration/site-configuration).