---
layout: post
title: Cheatsheets and Reference Cards
tags: ' #box(wikibox) '
box: wikibox
---

# Creating simple and shareable quick references

Cheatsheets can be used for quick reference, glossary, definition lists, any key value lists.

**Layout**

For CheatSheet View (Card Page) see Wikibox Layout Specification.

**Syntax**

A cheatsheet is a simple markdown file:

- Set layout to cheatsheet.
- Use title and line in frontmatter to add a title and description (optional).
- Use Markdown Definition Lists inside a h1 heading for your cheats. 
- Use a single endless line of text inside a h1 heading for info boxes.

After YAML Frontmatter:

	# GROUP

	TERM
	: DESCRIPTION
	TERM
	: DESCRIPTION

	# BOX

	TEXT

OR

	GROUP
	=====

	TERM 	: 	DESCRIPTION
	TERM 	: 	DESCRIPTION

	BOX
	====

	TEXT

- [Pandoc - Markdown Definition Lists](http://johnmacfarlane.net/pandoc/demo/example9/pandocs-markdown.html#definition-lists)
- [Kramdown - Markdown Definition Lists](http://kramdown.rubyforge.org/syntax.html#definition-lists)

**Sharing Formats**

Besides the YAML frontmatter cheatsheets are more or less a representation of classical grouped key-value pairs. Thus the written`markdown` file (definition lists) can easily be exported/imported in common standards las `XML` or `JSON`.

	---
	Standard YAML Frontmatter
	---
	<?xml version="1.0" encoding="UTF-8" standalone="yes"?>
	<reference>
    	<name>TIITLE</name>				// duplicates YAML title
    	<text>LINE</text>				// duplicates YAML line
		<group>
			<name>GROUP</name>
			<dl>
				<dt>TERM</dt>
				<dd>DESCRIPTION</dd>
			</dl>
		</group>
		<box>
			<name>BOX</name>
			<text>TEXT</text>
		</box>
	</reference>

**Comparison**	

HTML Definition lists are used to render groups.

	<dl>
		<dt>TERM</dt>
			<dd>DESCRIPTION</dd>
		<dt>TERM</dt>
			<dd>DESCRIPTION</dd>
	</dl>
