---
title: 4. Demo
layout: layouts/slide.liquid
---

Adding Pagefind search to [11ty.dev](https://11ty.dev), or a general guide to adding Pagefind to any site.

1. Clone the [Git Repo](https://github.com/11ty/11ty-website)
2. Follow Pagefind's [Getting Started](https://pagefind.app/docs/) guide, adding the Pagefind UI code to a search page (`src/docs/search.njk`)
3. Style Pagefind for the site using the CSS custom properties (`src/_includes/header.njk`):
  - ```
    body {
        --pagefind-ui-primary: #00bcd4;
        --pagefind-ui-text: #fff;
        --pagefind-ui-background: #222;
        --pagefind-ui-border: #eeeeee;
        --pagefind-ui-tag: #eeeeee;
    }
    ```
4. Check how your search results are looking. 
  - Use the `data-pagefind-ignore="all"` attribute to skip over headings or images as metadata
  - Use the `data-pagefind-ignore` attribute to remove any content that you don't want to be indexed
6. Set `data-pagefind-body` to limit search to a set of specific pages
  - In this case using the existing front matter attribute in `src/_includes/layouts/main.njk`:
  - ```
    if not excludeFromSearch
    ```
7. Add a filter! You likely have some sort of categorization rendered in your template already, so hook into that!
  - Wrapping `<span data-pagefind-filter="section">` around the breadcrumb is a good start here
