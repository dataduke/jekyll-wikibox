# jekyll-wiki

This project is supposed to serve as foundation of a responsive and flexible guerilla wiki for hackers.
It transfers your markdown/textile notes to satic html layout inspired by sublime text editor.

![Demo Version 0.1](https://raw.github.com/dataduke/jekyll-wiki/master/%E2%80%8Edemo-v01.jpg)

## Change History

- **Version 0.1** Inital commit, not working

## Implemented Features

- multiple boxes/repositories (blogs) for notes (markdown, textile)
- sort by date created

## To Be Done

- basic layout  
  - fix horizontal scrolling
  - post layout
  - box layout
- advanced layout
  - card stack view
- sorting
  - sort by date modified
  - sort by category
  - sort by tags
  - sort by name
- set content column width
  - 300px
  - 600px
  - 900px
- switch scrolling for post
  - horizontal
  - vertical 
- markup
  - add syntax highlighting
  - add mathjs
- special cards
  - add support for .taskpaper files
  - add support for learning card attribute (POI pile of index cards)
- attachment and image support
  - attachment folder has same name as post (sits in same directory)
  - create automatic links to images in attachment folders
  - add support for post/card attachments (contained in post-name-folders)
- search
  - add search box in sidebar
- themes
  - build theme Simple Github / jekyll-bootstrap with [twitter theme](http://themes.jekyllbootstrap.com/)
  - build theme [Apple Wiki](https://developer.apple.com/technologies/ios/)
  - build theme [FoldingText Website](http://www.foldingtext.com/)
  - build theme paint-pot-like (website suitable)
  - build theme scientific thesis (website suitable)
  - add theme switcher
- individual columns
  - show/hide boxes on landing page
  - change view/sorting of each box individually
- small appify
  - launch local website in safari via alfred app
  - search local website in safari via alfred app
  - only create local relate links that don't need a webserver (static html only), like:
    `<a href='./folder/2011-12-29-jekyll-introduction.html' title='Jekyll Introduction'>Jekyll Introduction</a>`
- big appify (maybe not to be done)
  - create browser app which wraps all dependencies (jekyll, ruby)
  - implement toggle to source view on post layout
  - allow editing inside source view
  - separate/strip boxes to folders outside of app
  - allow only custom folder path for boxes outside of wiki instance
- mobile appify
  - make it deployable via dropbox for mobile use (ios, android)

## References

### Core Technologies

- [ruby](http://www.ruby-lang.org/en/)
- [jekyll](https://github.com/mojombo/jekyll)
- [jekyll-bootstrap](https://github.com/plusjade/jekyll-bootstrap) 
- [multi-blog-jekyll](https://github.com/ggarron/multi-blog-jekyll)

### Related Technologies

- [github pages](http://pages.github.com/)  
- [github pages help](https://help.github.com/categories/20/articles) 

### Design Inspirations

- [Sublime Text](http://www.sublimetext.com/)
- [Soda-Dark.sublime-theme](https://github.com/buymeasoda/soda-theme)
- [Monokai-Soda.tmtheme](https://github.com/simeonv/st2-color-schemes)

### Markup Languages

- [markdown](http://daringfireball.net/projects/markdown/) by John Gruber
- [multimarkdown](http://fletcherpenney.net/multimarkdown/) by Fletcher Penny
- [textile](http://textism.com/tools/textile/) by Dean Allan
- [taskpaper](http://www.hogbaysoftware.com/products/taskpaper) by Jesse Grosjean