---
layout: post
title: Conventions
tags: ' #box(wikibox) '
box: wikibox
---

# Conventions


# Rule

- Don't trust meta data saved by file systems (or open meta tags) for lifetime storage. They easily get crappy when switching disks or filing systems. 
- Use YAML frontmatter at every file

# Item Type

card, box, stack, area, board.

## Frontmatter

The frontmatter mainly uses YAML. Nested inside `tags:` a domain-specific language is used, which can be read from cli grep.
	
	layout:			// item layout

	category:		// item type; NOT RECOMMENDED -> use tags: #item(NamedType)
	box:			// card filing; NOT RECOMMENDED -> use tags: #box(NamedBox)

	date:			// created
	edit:			// modified	
	
	title:			// item title
	line:			// context-based title addition (see description below)

	tags:			// characterize a card with attributes for processing (see file tagging)
	
	files:			// attached files (attachments)

**Line** 

can be used as description, synopsis, abstract, subtitle, preview, teaser or question answered in content. So this line can be very useful in many ways.

# File Tagging

Reserved hashtags:

	#box(NamedBox)		// for allocating a card to a box
	#stack(NamedStack)
	#area(NamedArea)
	#board(NamedBoard)

	#item(NamedType)	// same as YAML Frontmatter category
	#cat(NamedCategory)	// personal category of an item

	#pom(1)		// counts the needed worktime of a card in pomodoros (time units of 25 min.)
	#pom 		// pom without a value defaults to 1.

	#star		// starred card (used for highlighting via CSS)

	#toc		//  adds a generated table of contents between frontmatter and content
	#toc(2)		//	toc untill depth level of <h2> headlines

	#share(SeviceName) 		// shares card url with title and line  
	#share(person@mail.com) // share card url with title and line

	#mail(person@mail.com) // sends title, line and content via mail to person

**Item Type and Categories**

Category tag and YAML category differ. YAML category describes the item type (card, box, stack, area, board) and category tag describes a personal meaningful category (e.g. dev - development, pro - productivity).

Instead of the YAML frontmatter category one can use item tag to specifiy the item type.

**Share**

You can specify a service like twitter to automatically share your published card (post).

**Mail**

Mails can be written as a card and by invocation of a script be sent with formatted markdown.

# Naming

- CamelCase names for easy finding.

## Folder Structure

- box/NamedBox/Date-Title.ext
- stack/NamedStack/index.md
- board/NamedBoard/index.md
- area/NamedArea/index.md

The index files contain rules to collect cards from boxes. The use the YAML frontmatter of each card, in specific date, edit, title and tags (sometimes category, attachments).
