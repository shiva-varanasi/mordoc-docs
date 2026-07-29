---
title: Change Management with Git
description: Use Git and platforms like GitHub or GitLab to manage documentation changes with the same rigour as source code.
---

Your documentation lives in files — Markdown pages, YAML configuration, images. Keeping those files in a Git repository turns your documentation project into something much more powerful than a shared folder of text files.

This page explains how to manage documentation changes with Git and why the content as code approach makes that possible.

## Why Git suits documentation

Software teams have used Git for decades because it solves real problems: tracking who changed what and when, reviewing changes before they go live, recovering from mistakes, and coordinating work across a team without people overwriting each other.

Documentation has exactly the same problems.

When your docs live in Markdown files under version control:

* Every change is recorded with the author, timestamp, and a reason
* Reviewers can see precisely what changed before anything is published
* Mistakes are a `git revert` away
* Multiple contributors can work in parallel on separate branches

This is the core idea behind content as code: treat documentation with the same engineering discipline as software.

## The basic workflow

A typical documentation change follows this pattern:

1. Create a branch for the change
2. Edit pages, configuration, or assets
3. Commit the changes with a short description
4. Push the branch to your remote repository
5. Open a pull request or merge request for review
6. Merge into the main branch when approved
7. Build and deploy the updated documentation

## Create a branch

Rather than editing the main branch directly, create a branch for each change:

```bash
git checkout -b update-installation-guide
```

Name the branch after the change. Names like `update-installation-guide` or `add-french-translation` tell reviewers what to expect before they open a single file.

Working on a branch keeps your changes isolated until they are ready. The main branch stays stable and always reflects what is currently published.

## Commit your changes

Once you have edited your files, stage and commit them:

```bash
git add .
git commit -m "Update installation steps for Node 22"
```

Write a short, clear message that describes what changed and why. Good commit messages help reviewers understand the intent and make it easy to trace a change months later.

For larger changes, use a multi-line message:

```bash
git commit -m "Rewrite authentication guide

Replace the old token flow with the new OAuth2 walkthrough.
Closes issue #48."
```

## Push and open a pull request

Push the branch to your remote repository:

```bash
git push origin update-installation-guide
```

Then open a pull request on GitHub or a merge request on GitLab through the platform's web interface.

A pull request shows reviewers a precise diff — exactly which lines were added, changed, or removed. Reviewers can leave inline comments, request revisions, or approve the change. Nothing merges until it is ready.

This review step is one of the clearest advantages of content as code. On a wiki or in a shared document, changes go live immediately. With a pull request, every change passes a review before readers see it.

## Protect the main branch

Most Git platforms let you protect the main branch so it cannot be pushed to directly. Changes can only reach it through a reviewed and approved pull request.

This means your published documentation is always in a known good state. A typo or broken link on an unreviewed branch cannot affect readers until a reviewer catches it and approves the fix.

Set up branch protection rules as early as possible. It is a small configuration change with a significant impact on documentation quality.

## Connect to a build and deploy pipeline

Once changes merge to the main branch, you still need to build and deploy the site. You can do this manually — run `npm run build` and upload `dist/` — or automate it with a CI/CD pipeline.

A common setup:

* On every pull request: run the build to confirm the content builds without errors
* On every merge to main: run the build and deploy automatically

GitHub Actions, GitLab CI, and similar tools support both steps. When the pipeline is in place, merging a pull request is the only manual step required to publish a documentation change.

## Use the history

Over time, your commit history becomes a record of how the documentation evolved. You can answer questions like:

* When was this page added, and by whom?
* Why was this configuration value changed?
* What documentation shipped alongside the last product release?

Clear commit messages and branch names make this history useful rather than just decorative.

## Next step

- [Build your site](/publishing/build-your-site).
