---
title: Customizing pages
description: Learn how to get the most out of UnMarkDocs
---
## About Front Matter
Page customization is done using Front Matter. Front Matter is a yaml-like block you can add to the top of your Markdown files separated by three hypens:
``` yaml
---
config1: myvalue
moreComplexSetting: 
    toggle1: true
    title: My Title
anotherSetting: 1
---
# Your Markdown file starts here
```

UnMarkDocs offers a wide range of options you can customize in every page.

## UnMarkDocs Options
### Title
Controls the title of the page.
``` yaml
title: My awesome page
```
!!! info
# Automatic title detection
If you don't specify a title, we'll try to guess it from your file.
!!!


### Description
Controls the description of the page
``` yaml
description: This page is very useful
```

### Next
Allows you to provide a *[CTA]: [Call to Action] to a URL or another page of the documentation at the bottom of the current page.

There are two ways to use this option:
``` yaml
next: slug-of-another-page # Or a URL

next:
    url: slug-of-another-page # Or a URL
    copy: Text to add to the bottom of the page instead of the default
```

### Pin
Allows to protect the page content with a numeric pin. The content of the page will be obfuscated, and the user will be requred to enter your code to view it.
``` yaml
pin: 1234
```

### Mathjax
Allows to use Mathjax in the page. When enabled, you can add mathjax code by surrounding it with `$` or `$$`.
``` yaml
mathjax: true
```

### Rickroll
Rewrites all links on the page to Rick Astley's Never Gonna Give You Up video.
``` yaml
rickroll: true
```

### Konami
Allows to specify a URL or another page of the documentation the user will be redirected to upon entering the Konami Code.
``` yaml
konami: true
```