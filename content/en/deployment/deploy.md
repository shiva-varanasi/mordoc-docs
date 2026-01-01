---
title: Deploy
description: Deploy your built site by publishing the dist directory to your production infrastructure.
---

Once you are satisfied with your documentation in preview, you can deploy it by publishing the build output. Mordoc produces a static site, so deployment means making the contents of `dist/` available through your production web hosting.

# What you deploy

Before deploying, build your site:

```bash
npm run build
```

The build output is written to:

```
dist/
```

This folder contains your complete documentation website, including HTML pages, assets, and search files.

# Deployment model

Most production environments serve documentation sites by hosting static files behind a web server or CDN.

In this model:

* Your hosting environment provides the web server
* You upload or publish the files from `dist/`
* The web server serves those files to users

You do not deploy your source content (`content/`) or configuration files (`config/`). You deploy only the built output.

# Typical deployment steps

The exact procedure depends on your infrastructure, but the workflow is typically:

1. Run `npm run build`
2. Confirm the `dist/` directory contains the latest version
3. Copy or upload the contents of `dist/` to your hosting environment
4. Ensure your hosting environment serves `index.html` for directory paths

# Verifying a deployment

After deployment, verify:

* Pages load correctly from the published URL
* Side navigation works as expected
* Images and assets load correctly
* Search works

If something is missing, rebuild and redeploy the updated `dist/` directory.

---

If you have reached this point, you should now have a fully functional documentation website built with Mordoc. Well done.

