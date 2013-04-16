# jekyll-wikibox

A guerilla wiki for hackers based on plaintext files (markdown, textile, taskpaper) transformed into static html by jekyll. The default theme is inspired by sublime text editor.

- **[Features](#features)** or what is it about?
  - Functional Features
  - Appearance
- **[Usage](#usage)** or how can I exploit it?
  - Live Demo
  - Installation
  - Local Deployment
  - Web Deployment
  - Magic Tricks
  - Customization
  - Themes
- **[Project Planning](#project-planning)** or how can I hack it?
  - Important Files
  - Project Structure
  - Theme Development
- **[References](#references)** or how does it work?
  - Core Technologies
  - Related Technologies
  - Markup Languages
  - Higher-Level Languages
  - Feature Inspirations
  - Design Inspirations
  - Design Frameworks

## Features

### Functional Features

  - multiple boxes/repositories (blogs) for notes (markdown, textile)
  - sort by date created

### Appearance
  
  - Sublime Text Theme
  - Paint Bucket Theme
  - iOS Linen Theme

## Usage

### Live Demo

- Available via `branch gh-pages` (github pages)  
  `http://dataduke.github.com/jekyll-wikibox` (to be done)

### Installation

1. install ruby
2. install jekyll `$ sudo gem install jekyll`
3. fork/clone/check out this github project `$ git clone git://github.com/dataduke/jekyll-wikibox.git`

### Local Deployment

1. change to `$ cd ~/github/jekyll-wiki`
2. run `$ jekyll --server` 
3. open `http://localhost:4000/`

### Web Deployment

- GitHub Hosting: Please refer to github pages help.
- Other web hoster: Please refer to jekyll wiki/help.

### Magic Tricks

- Interactive Wallpaper: [desktopr.app](http://mac.appstorm.net/reviews/internet-reviews/desktopr-put-a-website-on-your-desktop/) (Mac OS X )
- Individual App: [fluid.app](http://fluidapp.com) (Mac OS X ), [fake.app](http://fakeapp.com/) (Mac OS X )

### Customization

    ./_config.yml           # configuration
    ./_themes/themename     # themes; move all files/folders contained in a theme to root folder (and override)

### Hacking Layouts with Parameters

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

    {% for post in site.posts %}
      {% capture b %}{{ post.box }}{% endcapture %}
      {% if content contains b %}
        <!-- do something with every post with YAML frontmatter of "box: box004" -->
        {% if content contains "showday" %}
          <!-- do something with dates, like display day -->
          Day : {{ post.date | date:"%A" }
        {% endif}
      {% endif %}
    {% endfor %}

### Themes

Folding Text [README](https://github.com/dataduke/jekyll-wikibox/tree/master/_themes/foldingtext)

![Folding Text](https://github.com/dataduke/jekyll-wikibox/raw/master/_themes/foldingtext/_foldingtext.jpg)

iOS Linen [README](https://github.com/dataduke/jekyll-wikibox/tree/master/_themes/ioslinen)  

![iOS Linen](https://raw.github.com/dataduke/jekyll-wikibox/master/_themes/ioslinen/_ioslinen.jpg)

Paint Bucket [README](https://github.com/dataduke/jekyll-wikibox/tree/master/_themes/paintpucket)  

![Paint Bucket](https://github.com/dataduke/jekyll-wikibox/raw/master/_themes/paintpucket/_paintbucket.jpg)

Sublime Text [README](https://github.com/dataduke/jekyll-wikibox/tree/master/_themes/sublimetext)  

![Sublime Text](https://raw.github.com/dataduke/jekyll-wikibox/master/_themes/sublimetext/_sublimetext.jpg)

## Project Planning

### Important Files

    ./README.md                       # contains general information
    ./CHANGELOG.md                    # contains version history
    ./BACKLOG.md                      # contains initial feature backlog (backup/reminder)
    ./JEKYLL-WIKIBOX.taskpaper        # contains planned features and current backlog

### Project Structure

    .
    |-- .info                         # can be ignored; used for project information only
    |-- .temp                         # can be ignored; used at development for backup of important files
    |-- _includes                     # used for building index pages
    |   |-- main-index-sidebar.md
    |   |-- main-index-box-N.md
    |   |-- box-N-index-sidebar.md
    |   |-- box-N-index.md
    |-- _layouts
    |   |-- default.html
    |   |-- post.html
    |-- _themes             
    |-- _site                         # not checked in; created by jekyll as deployment directory
    |-- _plugins 
    |   |-- additional-feature-X
    |-- assets                        # for layout dependencies only
    |   |-- css
    |       |-- style.css
    |   |-- img
    |   |-- js
    |   |-- favicon.ico
    |-- box000                        # box001-005; more boxes can be added/renamed/deleted
    |   |-- _posts
    |   |   |-- 2013-01-01-hello-world.markdown    # .md or .textile or .taskpaper
    |   |   |-- 2013-01-01-hello-world             # folder for post attachments
    |   |       |-- attachment-1.jpg
    |   |       |-- attachment-2.pdf
    |   |-- atom.xml
    |   |-- index.html
    |-- _config.yml
    |-- index.html
    |-- atom.xml

### Theme Development

**Best Practices and Conventions:**

1. **Markdown Editing:** Build a basic `theme.css` by styling a simple markdown text file (with the help of Marked.app this is superfast). Typically this stylesheet includes the styling of body fonts, headings (h1-h4), links, lists, sourcecode, blockquotes, definitions, tables, columns, dividers (hr) etc. This file can be used for general text editing, post previewing, printing etc. (Your basic theme.css should/could be print and mobile friendly.)

2. **Desktop Browsing:** Now create a `theme-ext.css` (or `theme-web.css`). This file will extend your basic `theme.css` to style navigation and external media elements. It should include the styling for header, navigation (bars, breadcrumb), footer, index (page body content), embedded media, etc. and maybe overwrite `theme.css` with a different background etc. For desktop browsing load both created stylesheets: `theme.css`, which renders your post texts, and `theme-ext.css` for nice navigation.

3. **Mobile Browsing:** If your basic `theme.css` doesn't satisfy the mobile browsing experience. Build a separate, custom and minimal `theme-mobile.css` without any dependencies on `theme.css` or `theme-extensions.css`.

4. Throw everything away and just use `bootstrap`! Just kidding.

## References

### Acknowledgments

To all jekyll builders.

### Core Technologies

- [ruby](http://www.ruby-lang.org/en/)
- [jekyll](https://github.com/mojombo/jekyll), [Stackoverflow](http://stackoverflow.com/questions/tagged/jekyll)

### Related Technologies

- [jekyll-asset-pipeline](https://github.com/matthodan/jekyll-asset-pipeline), [blogpost](http://matthodan.com/2012/11/22/jekyll-asset-pipeline.html)
- [jekkll-asset_bundler](https://github.com/moshen/jekyll-asset_bundler)
- [jekyll-bootstrap](https://github.com/plusjade/jekyll-bootstrap) 
- [multi-blog-jekyll](https://github.com/ggarron/multi-blog-jekyll)
- [github pages](http://pages.github.com/), [help](https://help.github.com/categories/20/articles) 
- [octopress](https://github.com/imathis/octopress)
- [ruhoh](http://ruhoh.com)

### Markup Languages

- [markdown](http://daringfireball.net/projects/markdown/) by John Gruber
- [multimarkdown](http://fletcherpenney.net/multimarkdown/) by Fletcher Penny
- [github flavored markdown](https://help.github.com/articles/github-flavored-markdown) by GitHub
- [textile](http://textism.com/tools/textile/) by Dean Allan
- [taskpaper](http://www.hogbaysoftware.com/products/taskpaper) by Jesse Grosjea

### Higher-Level Languages

- [YAML](http://www.yaml.org): data serialization;
- [liquid](http://www.liquidmarkup.org/) [github-repo](https://github.com/Shopify/liquid) [github-wiki](https://github.com/Shopify/liquid/wiki) [guide](http://wiki.shopify.com/UsingLiquid): template engine;
- [{{ mustache }}](http://mustache.github.com), [js-github-repo](https://github.com/janl/mustache.js): tag expansion;
- [Sass](http://sass-lang.com): CSS3 abstraction; .scss or .sass;
- [Haml](http://haml.info), [doc](http://haml.info/docs/yardoc/file.REFERENCE.html): HTML abstraction; .html.haml;
- [less](http://lesscss.org/), [github-repo](https://github.com/cloudhead/less.js): CSS3 extension for dynamic behaviour (variables etc.);
- [liquid](http://www.liquidmarkup.org/), [help](https://github.com/mojombo/jekyll/wiki/liquid-extensions), [github-repo](https://github.com/Shopify/liquid), [wiki](https://github.com/Shopify/liquid/wiki/Liquid-for-Designers): template system;
- [ERuby](http://de.wikipedia.org/wiki/ERuby), [erb](http://ruby-doc.org/stdlib-1.9.3/libdoc/erb/rdoc/ERB.html): Ruby templating; .erb, .html.erb, .xml.erb;
- [CoffeeScript](http://coffeescript.org/): JavaScript abstraction;

### Feature Inspirations

 - **PoIC** (Pile of Index Cards), [Wiki](http://pileofindexcards.org/), [Blog](http://pileofindexcards.org/blog/)

### Design Inspirations

- **Sublime Text** Theme, [Sublime Text Editor](http://www.sublimetext.com/), [Soda-Dark.sublime-theme](https://github.com/buymeasoda/soda-theme), [Monokai-Soda.tmtheme](https://github.com/simeonv/st2-color-schemes)

### Design Frameworks

- [jQuery UI](http://jqueryui.com/)
- [Twitter Bootstrap](http://twitter.github.io/bootstrap/), [github-repo](https://github.com/twitter/bootstrap)
