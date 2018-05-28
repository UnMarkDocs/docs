---
title: Configuring Custom Domains
description: A step-by-step guide to custom domains on UnMarkDocs
---

By default, your users can access your documentation on `yourproject.unmarkdocs.co`, but you'll probably want to use something fancier, like `docs.yourproject.com`. This guide will teach you how you can achieve that.

## Requirements
To follow this guide, you'll need two things:
- A custom domain to setup (obviously) and access to its DNS configuration
- An UnMarkDocs project
- An UnMarkDocs Premium account

## Pointing your domain to UnMarkDocs
First, you'll need to add a `CNAME` DNS record for your domain/subdomain pointing to `custom.unmarkdocs.co`. After you've done this, accessing your domain should show you an error message telling you there's no project configured with that domain.
!!! warning
# DNS Propagation
Take into account that DNS changes can take up to 24 hours to take effect.
!!!

## Linking your domain with your project
Now that you've pointed your domain to UnMarkDocs, you're ready to link it to your project. To do it, navigate to your project settings page from your dashboard, add your domain on the `Domain` input and click `Update Domain`.

## Enabling SSL for your domain
The easiest way to get SSL up and running on your custom domain is to use Cloudflare. The process in widely documented, and Cloudflare even has an [informative page about it](https://www.cloudflare.com/ssl/).

## Troubleshooting & help
If you find any problems when going through any of this steps, feel free to drop us an email at [domains@unmarkdocs.co](mailto:domains@unmarkdocs.co) and we'll be happy to help you :smile: