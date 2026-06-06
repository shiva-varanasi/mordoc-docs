---
title: Deploy Your Site
description: Publish the built dist folder to your company's hosting environment.
---

Deploying a Mordoc site means uploading the built files from `dist/` to your hosting environment.

You do not deploy your Markdown files or configuration folders directly.

## What you publish

Publish everything inside:

```text
dist/
```

That folder was created when you [built your site](/publishing/build-your-site). It contains the complete static website, including HTML pages, assets, search files, `sitemap.xml`, and `robots.txt`.

Do not upload:

* `content/`
* `config/`
* `public/`
* `node_modules/`
* Source project files

Readers should only receive the built site from `dist/`.

## How static hosting works

Mordoc produces a static website.

That means:

* Pages are served as files
* No application server needs to run your documentation
* A web server or CDN can host the site directly

Your infrastructure team may use object storage, a CDN, a static hosting service, or a simple web server. The exact tool depends on your company.

The important part is the same in each case: publish the contents of `dist/`.

## Typical deployment steps

Most teams follow a workflow like this:

1. [Build the site](/publishing/build-your-site)
2. [Preview the built site locally](/publishing/preview-before-publishing)
3. Upload or publish the contents of `dist/`
4. Point your public documentation URL at the hosted files

If your team uses continuous deployment, the build step may run automatically when changes are merged. The deploy step still publishes the generated `dist/` output.

## Verify the live site

After deployment, open your public documentation URL and check:

* The homepage loads
* Sidebar and top navigation links work
* Images, logos, and downloads load correctly
* Search returns expected results
* Shared links show the right title and preview image

If something is missing, fix the source project, rebuild, and deploy the updated `dist/` folder again.

## Keep baseUrl accurate

Make sure `baseUrl` in `config/site.json` matches the live site address before you build for production.

If the address changes later, update `baseUrl`, rebuild, and redeploy.

This keeps canonical links, `sitemap.xml`, and social previews pointed at the correct website.

## You are ready

You now have a full path from writing content to publishing a company documentation site with Mordoc.

If you need to look up the source projects behind Mordoc itself, see [Source Repositories](/references/github-repo).
