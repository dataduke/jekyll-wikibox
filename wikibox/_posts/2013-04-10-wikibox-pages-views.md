---
layout: post
category: cat001
comments: true/false.
date: 2013-04-10 21:35
edit: 2012-04-15
title: Graphical Specification
tags: ' #box(wikibox) #board(dev) #toc #star #prio(1) #study(5) #cat(dev) #public #share(Person)'
line: Line can be used as description, synopsis, abstract, subtitle, preview, teaser or question answered in content. So this line can be very useful in many ways.
box: wikibox
---

# Navigation, Pages and Views

Below follows a list of different views with a short description for their possible view.

## Navigation

Layout of header with breadcrumb-navigation, area-navigation, board-navigation, boxes-navigation and stack-navigation.
	
	Breadcrumb                             Y Y				
	--------------------------------------------
	X  !sitelogo 	|	Areas     /    Boards
	X				|---------------------------
	X	Sitename	|	Boxes     /     Stacks
	-------------------------------------------
	   			 	 		View / Sort
	-------------------------------------------

					Content

	-------------------------------------------
	   Command


Three `X` icons/buttons: 

- Toggle Breadcrumb Bar
- Toggle Areas/Boards Bar
- Toggle Boxes/Stacks Bar

### Breadcrumb Bar

Bar shows navigation path. (maybe fixed position topbar)

	SiteName > BoxName > Date-Title [Star] [Paperclip]       Y Y

Two `Y` Icon/button:

- Collapse all headers = show table of contents (only available in card page).
- Open original source file in external local text editor (via applescript)

### Areas/Boards Bars

Bar has the appearance of a shelf for areas and boards and shows all areas/boards with a glyphicon and a card count (like at NFL Goal boards).

	 !icon       !icon      !icon       !icon      !icon        !icon
	AreaName    AreaName   AreaName   BoardName   BoardkName   BoardName
	 #cards      #cards     #cards     #cards      #cards       #cards

### Boxes/Stacks Bar

Bar has the appearance of shelf for boxes and stacks and shows all boxes/stacks with a glyphicon and a card count (like at NFL Goal boards).

	 !icon       !icon      !icon       !icon      !icon        !icon
	BoxName     BoxName    BoxName    StackName   StackName   StackName
	 #cards      #cards     #cards     #cards      #cards       #cards

### View/Sort Bar

Bar for changing the layout of the content or resort all shown cards.

	View: List Card Full	Sort: Year Name Tags

### Command Bar

Consists of one big input field, for searching, filtering, navigating.

## Pages

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

## Views


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

### Snippets :View (Box Page)

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

### Article View (Card Page)

Article View displays the full file with all meta data and statistics of the file.

	Title:

	Created:				Day:
	Changed:				Day:
	Tags:						
	Line:

	Text: 000 words, O pomodoros

	Contents:

	- Content -


### Post View (Card Page)

A view for a public blog post.

	- Date - Title -

	- Contents -
	
	Comments:
