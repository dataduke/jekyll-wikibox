---
layout: post
title: Learning Systems
tags: ' #box(wikibox) '
box: wikibox
---

# Index Card Learning Method


## Croco 2-6-19

[Croco 2-6-X-19](http://www.youtube.com/watch?v=LnU53vjplI0) is a learning system based on index cards with questions written on the front and answers written on the back. 

It uses a pipeline of 19 boxes for index cards representing 19 learning days. 2-6-X-19 represents a box number. X is a chosen number between 6 and 19 for extra heavy answers.

Every card will be repetitively learned for a minimum of 5 times.

**Algorithm**

1. All new cards are put in box 1.
2. Everyday you go through all cards in box 1 to empty them completely.
2.1 If you **don't know the answer** of a card:
2.1.1 all marks on the card are erased
2.1.2 and the card is put back in box 1 (at the end of the stack)
2.2. If **you know the answer** of a card
2.2.1 for the 1st time (not marked), you mark the card with `I` and put it in box 2.
2.2.2 for the 2nd time (marked `I`), you mark the card with `II` and put it in box 6.
2.2.3 for the 3rd time (marked `II`), you mark the card with `III` and put it in box X.
2.2.4 for the 4th time (marked `III`), you mark the card with `IIII` and put it in box 19.
2.2.4 for the 5th time (marked `IIII`) you can put the card out of the pipeline. A good idea to archive cards in topic-based archive boxes with sections for each month.
3. When box 1 is finally empty
3.1. you shift all boxes forward (-1): E.g. box 2 gets box 1, box 6 gets box 5 etc.
3.2. Box 1 gets box19 and therefor put at the end of the pipeline.
4. Now you have the setup for the next day, with box 1 full of cards again.

**Pseudo-Code**

	initialize boxX as box12;
	initialize stackPos as start; // or end

	while (Stack of cards in Box1 > 0)
	{
		ask question;
		if (answer is false)
		{
			erase all marks;
			put card at end of stack in box 1;
		}
		if (answer is true)
		{
			switch (mark)
			{
				not marked: put card at stackPos of stack in box2;
				marked I: put card at stackPos of stack on box6;
				marked II: put card at stackPos of stack on boxX;
				marked III: put card at stackPos of stack on box19;
				marked IIII: archive card {
					put card in box with topic (get Topic of Card) 
					at beginning of stack of Year-Month Section (get Date of Card | %Y%M);
				}
			}
		}
	}
	for all boxes{
		box = box - 1;
	}


