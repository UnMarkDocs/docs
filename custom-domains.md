---
title: Configuring Custom Domains
description: A step-by-step guide to custom domains on UnMarkDocs
---

By default, your users can access your documentation on `yourproject.unmarkdocs.co`, but you'll probably want to use something fancier, like `docs.yourproject.com`. This guide will teach you how you can achieve that.

## Requirements
To follow this guide, you'll need two things:
- A custom domain to setup (obviously) and access to its DNS configuration
- An UnMarkDocs project

## Creating a Fly account
To setup your custom domain, we're going to use a website called [Fly.io](https://fly.io), so you'll need an account. You can create one [here](https://fly.io/app/sign-up).

## Creating a new Site
Now that you have a Fly account, you'll need to create a Site for your documentation website. To do so, fill out the form on [this URL](https://fly.io/sites/new?generic_type=own) filling your project's subdomain (`yoursubdomain.unmarkdocs.co`) on both input fields.
<details>
<summary>Screenshot</summary>

![screenshot of the form](https://i.imgur.com/edd2Z9r.png)
</details>

After submitting the form, you'll be given a temporary URL. Make sure to verify everything's working (except links, we'll fix that later).

Next, you'll be asked for a hostname, that is, the domain you want your docs served on. You probably want this to be `docs.yourproject.com`.
<details>
<summary>Screenshot</summary>

![screenshot of the form](https://i.imgur.com/qX9TAD6.png)
</details>

After that, you'll need to point your domain to the given one. This is a simple process, and it's good documented on Fly's end.

## Fixing "Not Found" error
Once the above process is complete, try to access the domain you configured. If your documentation page shows up, you can skip to the next section, but there's a chance you just get a "Not Found" error. Here's how to fix it.

1. Access the following URL: `https://fly.io/sites/YOUR_SLUG_HERE/backends`, your slug being your domain with hyphens instead of dots. For example, for `docs.myproject.com` the slug would be `docs-myproject-com`.
2. Click the edit button
3. Change `Origin hostname` and `Host` back to your UnMarkDocs subdomain and click `Update backend`.

That's it, your `Not Found` error should be gone now.

## Enabling SSL for your domain
Getting a SSL certificate for your domain is an easy process with Fly:

1. Access the following URL: `https://fly.io/sites/YOUR_SLUG_HERE/middleware`, your slug being your domain with hyphens instead of dots. For example, for `docs.myproject.com` the slug would be `docs-myproject-com`.
2. Search for `HTTPS Upgrader` in that page, and click the `Add` button.

Boom! HTTPS enabled! :closed_lock_with_key:

## URL rewrites
Although you may be able to see your site correctly, you may have noticed the links on the sidebar take you back to the UnMarkDocs subdomain. Fortunately, this has an easy fix.

1. Access the following URL: `https://fly.io/sites/YOUR_SLUG_HERE/rules/new`, your slug being your domain with hyphens instead of dots. For example, for `docs.myproject.com` the slug would be `docs-myproject-com`.
2. Scroll down to the `Rewrite Response` section
3. Fill the `Search Pattern (Regular Expression)` with your UnMarkDocs subdomain, escaping the dots. For example, for `example.unmarkdocs.co` you'd enter `docs\.myproject\.com`.
3. Fill the `Replacement` with your domain and click `Add routing rule`.
<details>
<summary>Screenshot</summary>

![screenshot of the form](https://i.imgur.com/yZOWORM.png)
</details>

Your navigation should work now! :tada:

## Troubleshooting & help
If you find any problems when going through any of this steps, feel free to drop us an email at [domains@unmarkdocs.co](mailto:domains@unmarkdocs.co) and we'll be happy to help you :smile: