---
layout: post
box: wikibox
title: Theme Development
tags: ' #box(wikibox) '
---

# Theme Development

## Best Practices and Conventions

1. **Standard View (Markdown Editing):** Build a basic `theme.css` by styling a simple markdown text file (with the help of Marked.app this is superfast). Typically this stylesheet includes the styling of body fonts, headings (h1-h4), links, lists, sourcecode, blockquotes, definitions, tables, columns, dividers (hr) etc. This file can be used for general text editing, post previewing, printing etc. (Your basic theme.css should/could be print and mobile friendly.)

2. **Desktop Browsing:** Now create a `theme-ext.css` (or `theme-web.css`). This file will extend your basic `theme.css` to style navigation and external media elements. It should include the styling for header, navigation (bars, breadcrumb), footer, index (page body content), embedded media, etc. and maybe overwrite `theme.css` with a different background etc. For desktop browsing load both created stylesheets: `theme.css`, which renders your post texts, and `theme-ext.css` for nice navigation.

3. **Mobile Browsing:** If your basic `theme.css` doesn't satisfy the mobile browsing experience. Build a separate, custom and minimal `theme-mobile.css` without any dependencies on `theme.css` or `theme-extensions.css`.

4. **Special Layouts** If you included additional layouts (cheatsheet view, presentation view) to standard layouts (article, post). It is best to add an additional stylesheet for each e.g. `theme-cheatsheet.css`. These files can be loaded as "Scoped CSS" inside the body of your additional layout. 

5. Throw everything away and just use `twitter bootstrap`! Just kidding.