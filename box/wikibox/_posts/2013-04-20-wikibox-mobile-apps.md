---
layout: post
title: Mobile Apps
tags: ' #box(wikibox) '
box: wikibox
---

# Mobile Apps

Mobile apps use are a simple tool for brwosing your (personal) knowledge base on the go.
An app serves as offline capable viewer for your cards and attached files with a sleek and minimalist interface.

## Interface

	------------------------------------
	  Y Y Y Y   |
	------------|
	Item >		|	
	------------|
	Item >		|		CONTENT
	------------|
	Item		|	
	------------|
	...			|
	------------|-----------------------
	X X X X X X |	command/search bar
	------------------------------------

## Functions

**Top Bar**

Buttons `Y` allow to sort currently visible column list view:

- name: tab to sort titles from A-Z, tab again to sort Z-A
- date: tab to sort reverse chronically, tab again to sort chronically
- cat: tab to sort grouped by category (as list separator)

**Bottom Bar**

Buttons `X` serves to change the left column.

Row 1:

- Toggle Icon: switches bottom bar to row 2.
- Box Icon: shows box folder (tap to browse a level deeper or open item - if deepest level)
- Stack Icon: shows stack folder (tap to browse a level deeper or open item - if deepest level)
- Area Icon: shows area folder (tap to browse a level deeper, or open item - if deepest level)
- Board Icon: shows board folder (tap to browse a level deeper, or open item - if deepest level)

Row 2:

- Toggle Icon: switches bottom bar to row 1.
- Star Icon: shows all starred cards/items (based on YAML frontmatter; aggregated from all places)
- Files Icon: shows all file attachments (based on YAML frontmatter; aggregated from all places)
- Assets Icon: shows assets folders (scripts/jobs, stylesheets etc.)
- Settings Icon: opens wikibox root folder and reveals browsing access to all folders. Especially helpful for access to layout  

**Command Bar**

The command bar consists of one hugh input field. The availibe command allow:

- to search globally or with scope (in box) 
- to filter a column view: (filter "text")
- to highlight a word in the content view
- to run a script globally or on specified items

Commands use natural language: 

- dates (before 2009, cards of 2nd friday on december 2009)
- places (search for "cats" in box "animals")
- ...

Command Bar is a _plugin to wikibox.

## Price

Also the source code is availible on github the apps are not free.

The pricing serves as a donation to back the development worktime needed for wikibox.