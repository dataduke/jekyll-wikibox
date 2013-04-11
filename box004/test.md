---
layout: post
box: box004
category: cat003
title: 'Tasks in Box 4'
date: 2013-01-01 01:01
---

jekyll-wikibox:
	A guerilla wiki for hackers based on plaintext files (markdown, textile, taskpaper) transformed into static html by jekyll. The default theme is inspired by sublime text editor. @sticky
Goals:
	- 1 App to rule them all approach
	- finshed product name: uberbox, uberwiki
	- default theme things taskpaper
Requirements:
	- use all space of 30 inch monitor (2560x1600) but also look good on iphone in portrait mode
	- be usable as wallpaper app
Use Cases:
	- store notes
Iteration 1:
	current cycle for next 2 weeks @sticky
	- basic layout  
		- fix horizontal scrolling
		- post layout
		- box layout
	- theme minimal
	- theme daring fireball
	- add mosaic view

	- split _config.yaml exclude theming parts to other .yaml file
	themes change colors and background of items but do never touch the structure of the weblayout webapplication @sticky 
	- enable support for taskpaper themes for taskpaper files
	- enable support for highlight.js themes for code highlighting

	- global asset path
	- sublimetext theme index.html include decor.md to asset txt/decobar.md
	- create theme: Minimal (black on grey or white): no colors/bold/underline, 
	- foldable headers, clean
	- linking notes
Iteration 2:
	- deprecate theme development (basic ideas are there, everybody can adapt them if wanted)
	- focus on pure feature support
	- use minimal theme or things theme
	- write promotion blogpost: the case against task management apps 
		- reference: alex panye everything in pockets
		- reference: pocket information douglas amberv posts in scrivener forums
		- what I wanr to achieve
		- present wikibox
Backlog:
	- live search/command line input field for content interaction (bottombar)
		- use known cli tools and command names for interaction (dont reinvent the wheel)
		- filter viewed content/items (columns stay in postion put only show results) all fields, by name, by category, by tags, by abstract, by file content (grep)
		- add box (past link to external directory, all files need to have yaml with boxname), box gets added dynamically
		- add note to box with timestamp date
		- delete note
		- delete box by name
		- change view
		- shrink sidebar to icons only as it isnt needed anymore
		- command show hide sidebar
		- switch space
		- switch theme

	- decided on javascript framework for interactive content
		- use angular ui

	- iintroduce boards/spaces/areas = set of boxes
		- each space has these preferences: name, icon, theme, boxes (folder paths).
	
	- advanced layout
		- card stack view
		- post line view  
		- show/hide box column by selesction in main view
		- allow drag and drop to sort columns

	- sorting
		- sort by date modified
		- sort by category
		- sort by tags
		- sort by name

	- set box/post/content column width
		- 300px
		- 600px
		- 900px
		- dynamic slider

	- switch scrolling for post
		- horizontal
		- vertical 

	- markup
		- add syntax highlighting
		- add mathjs

	- special cards
		- add support for .taskpaper files
		- add support for .rst file (reStructuredText)
		- add support for learning card attribute (see PoIC - Pile of Index Cards - http://pileofindexcards.org/ and http://pileofindexcards.org/blog/)

	- attachment and image support
		- attachment folder has same name as post (sits in same directory)
		- create automatic links to images in attachment folders
		- add support for post/card attachments (contained in post-name-folders)

	- add top bar
		- add search box on left
		- add breadcrumb path
		- filter box (for highlighting words in content area)

	- add config file
		- global font with font size
		- contains attributes for each box (box name, relative box path, box foreground color, box background color)
		
	- themes
		- seperate color compostions from theme layout
		- add mobile version (without fixed sidebars/topbars)
		- finish sublime text theme
		- build theme Simple Github / jekyll-bootstrap with [twitter theme](http://themes.jekyllbootstrap.com/)
		- build theme [Apple Developer Wiki](https://developer.apple.com/technologies/ios/)
		- build theme [FoldingText Website](http://www.foldingtext.com/)
		- build theme [docs](https://readthedocs.org/)
		- build theme paint-pot-like (website suitable)
		- build theme scientific thesis (website suitable)
		- build theme iOS linen
		- build theme Bianchi Celeste
		- add theme switcher
		
	- individual columns
		- show/hide boxes on landing page
		- change view/sorting of each box individually

	- wallpaper appify
		- let website be used as interactive fullscreen wallpaper
		@sticky for mac os x use: Desktopr http://mac.appstorm.net/reviews/internet-reviews/desktopr-put-a-website-on-your-desktop/

	- small appify
		- launch local website in safari via alfred app
		- search local website in safari via alfred app
		- only create local relate links that don't need a webserver (static html only), like:
		    <a href='./folder/2011-12-29-jekyll-introduction.html' title='Jekyll Introduction'>Jekyll Introduction</a> @sticky
		
	- big appify (maybe not to be done)
		- create browser app which wraps all dependencies (jekyll, ruby)
		- implement toggle to source view on post layout
		- allow editing inside source view
		- separate/strip boxes to folders outside of app
		- allow only custom folder path for boxes outside of wiki instance

	- mobile appify
		- make it deployable via dropbox for mobile use (ios, android)
		- every box has its own feed which is usable by rss-reader apps
