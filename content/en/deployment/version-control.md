---
title: Version Control with Git
description: Understand how version control helps manage, collaborate on, and publish your documentation.
---

As your documentation grows, it becomes important to track changes, collaborate safely, and maintain a reliable history of updates. Version control solves these problems.

# What is version control?

Version control is a system that records changes to files over time.

Instead of overwriting files manually or keeping multiple copies, version control allows you to:

* See what changed
* Know when it changed
* Know who made the change
* Restore earlier versions if needed

Git is the most widely used version control system and is commonly paired with remote version control services.

# Why use version control for documentation?

Documentation changes frequently. Version control provides structure and safety as those changes grow.

## Key benefits

* **Track changes**
  Understand exactly what changed between versions of your documentation.

* **Collaboration**
  Multiple people can work on content without overwriting each other’s changes.

* **History and recovery**
  Restore previous versions if a mistake is introduced.

* **Backup**
  Your documentation can be stored in a remote version control service, keeping it safe outside your local machine.

* **Review before publishing**
  Changes can be reviewed before they are built and deployed.

* **Deployment automation**
  Many teams use version control to automate builds and deployments.

## Content as code in practice

Mordoc is designed around the principle of treating documentation content as code — without forcing authors to think like developers.

Because your documentation lives in files:

* Changes are explicit and reviewable
* Version history is clear and reliable
* Collaboration scales naturally as your team grows

Version control enables this approach. It allows documentation to benefit from the same change management practices used in software development, while keeping the writing experience lightweight and focused.

This principle is a key differentiator between Mordoc and many traditional documentation tools.

# What goes into version control?

Typically, you store:

* Markdown files in `content/`
* Configuration files in `config/`
* Project asset files

You do **not** store:

* The `dist/` directory
* Build output files
* Generated or temporary files

The build output can always be regenerated.

# Next steps

* [Deploy](/deployment/deploy)