---
layout: post
date: 2013-04-10 21:35
edit: 2012-04-15
title: Layouts Specification
tags: ' #box(wikibox) #board(dev) #cat(dev) #public '
line: Layouts are basically html files placed in `_layouts` folder that can use the liquid template engine.
box: wikibox
---

# Navigation, Pages and Views

Below follows a list of different layouts with a short description for their possible use.

## Navigation Layouts

### Website

Layout of header with breadcrumb-navigation, area-navigation, board-navigation, boxes-navigation and stack-navigation.
	
	Breadcrumb                             Y Y				
	--------------------------------------------
	X  !sitelogo 	|	Areas     /    Boards
	X				|---------------------------
	X	Sitename	|	Boxes     /    Stacks
	-------------------------------------------
	   			 	 	[ View / Sort ]
	-------------------------------------------
	   			 	 	[ Description ]			
	-------------------------------------------

					Content

	-------------------------------------------
	   Command


Three `X` icons/buttons: 

- Toggle Breadcrumb Bar
- Toggle Areas/Boards Bar
- Toggle Boxes/Stacks Bar

Description and View/Sort are optional bars,
that are only shown when a area/board/box/stack is opened.

**Breadcrumb Bar**

Bar shows navigation path. (maybe fixed position topbar)

	SiteName > BoxName > Date-Title [Star] [Paperclip]       Y Y

Two `Y` Icon/button:

- Collapse all headers = show table of contents (only available in card page).
- Open original source file in external local text editor (via applescript)

**Areas/Boards Bars**

Bar has the appearance of a shelf for areas and boards and shows all areas/boards with a glyphicon and a card count (like at NFL Goal boards).

	 !icon       !icon      !icon       !icon      !icon        !icon
	AreaName    AreaName   AreaName   BoardName   BoardName   BoardName
	 #cards      #cards     #cards     #cards      #cards       #cards

**Boxes/Stacks Bar**

Bar has the appearance of shelf for boxes and stacks and shows all boxes/stacks with a glyphicon and a card count (like at NFL Goal boards).

	 !icon       !icon      !icon       !icon      !icon        !icon
	BoxName     BoxName    BoxName    StackName   StackName   StackName
	 #cards      #cards     #cards     #cards      #cards       #cards

**View/Sort Bar**

Bar for changing the layout of the content or resort all shown cards.

	View: List Card Full	Sort: Year Name Tags


### (Web) Application

See CardStackr Project. Multiple Instances possible for website, tasks, cards, company repository / workspace.

				 |
	+ Add Tag	 |    |BOX___________________|	     	// COMMAND BAR
				 |    
	Tag          |      View |___| Sort |___|      		// View Sort (optional)
	- Name (5)   |	          	  
	- Name (1)   |	         CONTENT 	  
			     | 
	Box          |    |---------------------|
    - Inbox (20) |    |       Card        X |
    - Journal(5) |    |---------------------|
	- Gymlog(3)  |   
	...	         |    |---------------------|
    	         |    |       Card        X |
	Project      |    |---------------------|
    - Name(3)    |
	...          |    |---------------------|
                 |    |       Card        X |
    Area         |    |---------------------|
    - Fitness (9)|
    - Dev (2)    |     << < 1 2 3..10..20 >>		 // Pages (optional)
    ...		     |

**Sidebar**

At the sidebar you can add tags (As quick filters or saved searches).

- Complex Tags like box(name), areea(name), project(name) are getting their own section.
- Simple Tags like star, public, ... are added to Tag section.

Possibly useful boxes: 

- Inbox
- Journal (Daily (Web)Diary)
- Gymlog
- Snippets (Code Listings)
- Cheatsheets

Possible useful can be supersection:

- Inbox, Drafts (Incomplete/Unfinished), Archive.
- Active, On Hold, Templates

**Command Bar**

Consists of one big input field, for searching, filtering, navigating, change view or sort.
Maybe command bar can have a dropdown box in beginning to search inside one box only.

**Content**

Shows content as endless scroll or with pages to turn.

**View/Sort Bar (optional)**

Two dropdown boxes to change thes criteria.

**Cards**

- have a fixed height, with the ability to scroll inside
- can be edited directly inside the card
	- click Button`X` to toggle between rendered view/edit mode
	- doubleclick Button`X` to open in external editor (VIM)
- can be opened individually on a single page (double click title)
- can be edited in single page

## Page Layouts

### Board and Area Page
 
A board page has several columns/slots, in which cards can be placed (2 Dimensions). 

	X	X	X	X	X
	X	X	X		X	
	X	X			X	
		X			X
		X

Columns can be:

- a complete box of cards.
- a random stack of cards.

Semantic Differences between a Board and a Area:

- A area is a persistent container for boxes and stacks, that are fixed to a field or supercatgory (e.g. Work).
- A board is a temporary collection for boxes and stacks, that might includ a lot of movement (e.g. Kanban or Scrum Board).

### Box and Stack Pages

A box or a stack page is a single column or stream of cards (1 Dimension).

	\/
	/\
	\/
	/\
	\/
	/\

Semantic Differences of a Box and a Stack.

- A box serves as persistent container (storage) for cards, that are tightly coupled by a specific attribute.
- A stack is a temporary collection (bundle) of cards, that are only loosely connected for a period of time.

### Card Page

Here a single card is rolled out (Focused View).

	\     /
	 \   /
	  \ /
	  / \
	 /   \
	/     \

## Content Layouts

### Simple View

A list of all items

	* Title
	* Title
	* Title

### List View (Board Page, Box Page)

A list of all items (with a possible list seperator fitting to sorting type (e.g. year)).

					- Year/Category - 
	 [Paperclip] [Star] * Date Title Words [Boxname/icon]
	 [Paperclip] [Star] * Date Title Words [Boxname/icon]
	 [Paperclip] [Star] * Date Title Words [Boxname/icon]
	 [Paperclip] [Star] * Date Title Words [Boxname/icon]
					- Year/Category - 
	 [Paperclip] [Star] * Date Title Words [Boxname/icon]
	 [Paperclip] [Star] * Date Title Words [Boxname/icon]
	 [Paperclip] [Star] * Date Title Words [Boxname/icon]

- Star-Icon is only shown if a note is tagged with star.
- Paperclip-Icon is only shown if there are file attachments to a card.
- Boxnames or Box-Glypicons can be used to identify boxes, when all posts are viewed or cards from different boxes. (Add glypicon to navigation bars beside count of cards. or above boxnames)

### Card View (Box Page)

A complete index card.
	
					- Previous Card - 
	
	*****************************************************
	* Title: Title (- words -)		Created: 0000-00-00 *
	* Tags:	#tag #tag				Changed: 0000-00-00 *
	*****************************************************
	* Line:												*  // 1 line
	* Content:											*  // 5-10 lines
	* 													* 	
	* 		- scrollable field with fixed heigth -		* 
	* 													* 		
	* 													* 		
	*****************************************************
	* /category/box/date-title.md 				EDIT	* // external/local editor
	* ,/Attachment.odf 							VIEW	* // mac preview
	*****************************************************

					 - Next Card -

### Study View (Box Page)

A simplified index card for learning purpose with question and answer in separate tabs.

			  - Previous Card -

	*************************************
	* Title:			  	  - words - *
	* Tags:								*
	*************************************
	* Line: Question  * Content: Answer *
	*				  *******************
	*									*
	*									*
	*									*
	*************************************

				- Next Card -

Maybe a simple markdown table in one file with 2 columns (question/answer) is better, where the answer column consists of covered/hidden fields, that can be opened. 

### Content View (Board Page, Box Page)

Pure content view can be used for boards, like: next action board, scrum/kanban board, drafting a storyline for presentations etc.

		     - Previous Card -

	*************************************
	*									*
	*	 		- Content -				*
	*									*
	*************************************

			   - Next Card -

### Mosaic View (Board, Box Page)
	
Small card snapshot in float layout from bird's eye perspective

	*******	  *******   *******   *******
	*  1  *	  *	 2  *   *  3  *   *  4  *
	*******   *******   *******   *******

	*******   *******   *******   *******
    *  5  *   *  6  *   *  7  *   *  8  *
	*******   *******   *******   *******

### Meta View (Box Page)

A 2 column view showing all meta data.

	| - Created -				|	- Title  -	(- words -)	| 
	| - Changed -				|	- Line - 				|
	| - Tags -					|	(- Table of Contents -) |
	|							|							|	

### Full View (Box Page)
						
A 2 column list of posts. Left column: All meta data. Right column:  content

	| Title:		(- words- )	|		- Content -			| 
	| Tags:						|							|
	| Created:					|							|
	| Changed:					|							|
	|							|							|	
	| Line:						|							|
	|							|							|
	| Contents:					| 							|
	| - Table of Contents- 		|							|

### Notational View (Box Page)

A 2 column view with a item list on the left and the selected item on the right like in travis web or notational velocity.

	|	,____________,			|							|	
	|	|____________| FILTER	|	Selected Item		 	|	
	|							|							|	
	| -------------------------	|	- Title -				|
	| - Title - 	(- words- )	|	- Line -				| 
	| - Created -  - Changed -	|							|
	| - Tags -					|	- Table of Contents -	|
	| -------------------------	|							|
	| - Title - 	(- words- )	|	- Contents -			| 
	| - Created -  - Changed -	|							|
	| - Tags -					|							|
	| -------------------------	|							|
	| - Title - 	(- words- )	|							| 
	| - Created -  - Changed -	|							|
	| - Tags -					|							|
	| -------------------------	|							|

### Paper View (Card Page)

A 2 column view of a card in scientific paper publication form.

	|	- title	-				|	   - continung -		|
	|	- date -				|	 - content col 2 -		|
	|							|							|
	|	- line - 				|							|
	|	(bold = abstract) 		|							|
	|							|							|
	|	Table of Contents   	|	  References:			|
	|							|							|
	|	- content col 1 - 		|							|

### Thesis View (Card Page)

	Title

	Line (meta information like university, )

	Table of Contents

	Table of Figures


### Book View (Card Page)

### Article View (Card Page)

Article View displays the full file with all meta data and statistics of the file.

	Title: WordCount

	Created:				
	Changed:
	
	Tags:						
	
	Attachments:

	Line:

	Contents:

	- Content -

### Post View (Card Page)

A view for a public blog post.

	- Date - Title -

	- Contents -
	
	[Comments:]

Blog post are only shown when tagged with `#public`.
Comments are only shown if YAML `comments: true` or if tagged with `#public(comments)`.

### Page View (Card Page)

	- Title -

	- Line - 

	- Contents -

### Plain View (Card Page)

The most basic layout. Only shows the content.

	- Content -

### Presentation View (Card Page)		

Basically presentation view offers an endless scrolling html page. As plaintext format (html, css etc.) it is closer related to LaTeX Beamer or troff presentations than to the commonly known 
presentation programs. 

	-----------------
	- Slidetitle -

	- Slidecontent -

	 NR NEXT 				// button to scroll down to next slide
	-----------------
	- Slidetitle -

	- Slidecontent -

	 NR NEXT PREVIOUS 		// button to scroll up
	-----------------

The slide `NR` and `NEXT`, `PREVIOUS` buttons have the same screen position when scrolled to divider line. They are generated automatically. Alternatively you can use a keyboard shortcut to scroll one slide up/down (eg. `SHIFT-UP/DOWN-ARROW`).

### Cheatsheet View (Card Page)

An optimized layout for viewing cheatsheets or quick reference sheets. It uses columns and endless vertical scrolling. Each cheatsheet file can define its column count individually as parameter.	Columns are filled up in order under the condition to have approximately the same content height in the end.

	TITLE
	LINE

	- GROUP -  	   (1) | - GROUP - 		(3)	| - GROUP -      (5)
	TERM   DESCRIPTION | TERM   DESCRIPTION | TERM   DESCRIPTION
	TERM   DESCRIPTION | TERM   DESCRIPTION | TERM   DESCRIPTION
	TERM   DESCRIPTION | TERM   DESCRIPTION | TERM   DESCRIPTION
	TERM   DESCRIPTION | TERM   DESCRIPTION | TERM   DESCRIPTION
	TERM   DESCRIPTION | TERM   DESCRIPTION | 
	TERM   DESCRIPTION | TERM   DESCRIPTION | - GROUP -      (6)
					   | TERM   DESCRIPTION | TERM   DESCRIPTION
	- GROUP -	   (2) |  					| TERM   DESCRIPTION
	TERM   DESCRIPTION | - BOX -	    (4) | 
	TERM   DESCRIPTION | TEXT	    		| 
	TERM   DESCRIPTION | 				    |


- `GROUP` can be a command group, category, topic. Groups are organized in columns.  
	- `TERM` can be a program shortcut, definition, term, vocabulary.  
	- `DESCRIPTION` is the corresponding explanation.  
- `BOX` boxes can add additional value.
	- `TEXT` can be helpful facts or background information about groups. Written as automatically wrapped text (multi-line).

### Report View

Adds graphical bars for metrics [5/10].

### Training View

For training plans.

### Agenda View

For events and calenders.