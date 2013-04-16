---
layout: post
title: Hacking Liquid Layouts
tags: ' #box(wikibox) '
line: For the visual basic style refer to the layout specification.
box: wikibox
--

# Hacking Layouts with Parameters

The files `./index.html` and `./box000/index.html` define the index pages. There (ex: `./box004/index.html`), the choosen layout (in YAML frontmatter, ex: `index-posts-1`) and a parameter list for the choosen layout (as content, ex: `box004`) have to be defined:

    ---
    layout: index-posts-1
    title: Box 4
    navigation: true
    navtitle: Box 4
    navpos: 5 
    ---
    box004 showday

Inside the choosen layout file (ex: `./_layouts/index-posts-1.html`) the parameter list is refereed to by the liquid template variable `content` in line 3 and 5:

    {% raw %}
    {% for post in site.posts %}
      {% capture b %}{{ post.box }}{% endcapture %}
      {% if content contains b %}
        <!-- do something with every post with YAML frontmatter of "box: box004" -->
        {% if content contains "showday" %}
          <!-- do something with dates, like display day -->
          Day : {{ post.date | date:"%A" }}
        {% endif}
      {% endif %}
    {% endfor %} 
    {% endraw %}

