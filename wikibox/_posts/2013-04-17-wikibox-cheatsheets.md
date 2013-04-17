---
layout: post
title: Cheatsheets
tags: ' #box(wikibox) '
box: wikibox
---

# Creating simple and shareable quick references

**Layout**

For CheatSheet View (Card Page) see Wikibox Layout Specification.

**Sharing Formats**

Besides the YAML frontmatter cheatsheets are more or less a representation of classical grouped key-value pairs. Thus the written`markdown` file (definition lists) can easily be exported/imported in common standards las `XML` or `JSON`.

	<group>
		<name>GROUP</name>
		<pair>
			<key>TERM</key>
			<value>EXPLANATION</value>
		</pair>
	</group>
	<box>
		<name>BOX</name>
		<text>DESCRIPTION</text>
	</box>