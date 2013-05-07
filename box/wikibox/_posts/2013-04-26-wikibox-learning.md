---
layout: post
title: Learning Boards and Systems
tags: ' #box(wikibox) '
box: wikibox
---

# Card Learning Methods

A learning method can be implemented as special board with e.g. 19 stacks (boxes) of cards.

## Croco 2-6-19

[Croco 2-6-X-19](http://www.youtube.com/watch?v=LnU53vjplI0) is a learning system based on index cards with questions written on the front and answers written on the back. 

It uses a pipeline of 19 boxes for index cards representing 19 learning days. 2-6-X-19 represents the box numbers for filing of correctly answered cards. X is a individually chosen number between 6 and 19 for extra heavy answers.

Every card will be repetitively learned for a minimum of 5 times.

**Algorithm**

1. All new cards are put in box 1.
2. Everyday you go through all cards in box 1 to empty it completely.  

	2.1 If you **don't know the answer** of a card:  
	2.1.1 all marks on the card are erased  
	2.1.2 and the card is put back in box 1 (at the end of the stack)  
	
	2.2 If **you know the answer** of a card:  
	2.2.1 for the 1st time (not marked), you mark the card with `I` and put it in box 2.  
	2.2.2 for the 2nd time (marked `I`), you mark the card with `II` and put it in box 6.  
	2.2.3 for the 3rd time (marked `II`), you mark the card with `III` and put it in box X.  
	2.2.4 for the 4th time (marked `III`), you mark the card with `IIII` and put it in box 19.  
	2.2.5 for the 5th time (marked `IIII`) you can put the card out of the pipeline. A good idea to archive cards in topic-based archive boxes with sections for each month.

3. When box 1 is finally empty

	3.1 you shift all boxes forward (-1): E.g. box 2 gets box 1, box 6 gets box 5 etc.  
	3.2 Box 1 gets box 19 and therefor put at the end of the pipeline.

4. Now you have the setup for the next day, with box 1 full of cards again.

**Pseudo-Code**

	initialize Box-X as Box-12;
	initialize StackPos as Start of Stack; // or as End of Stack

	for each Day {
		for each Card of Box-1 {
			while (Stack of Cards in Box-1 > 0 Cards)
			{
				ask Question of Card;
				if (Answer is false) {
					erase all Marks of Card;
					put Card at End of Stack in Box-1;
				}
				if (Answer is true) {
					switch (Mark) {
						not Marked: put card at StackPos in Box-2;
						I: put card at StackPos in Box-6;
						II: put card at StackPos in Box-X;
						III: put card at StackPos in Box-19;
						IIII: archive Card {
							put Card in Box with Topic (get Topic of Card) 
							at Start of Stack of Year-Month Section (get Date of Card | %Y-%M);
							// or sort chronologically with Year-Month Seperator
						}
					}
				}
			}
		}
		option 1:
			for each Box
			{
				if (BoxNumber == 1) {
					BoxNumber = Box-19;
				}
				else {
					BoxNumber--;
				}
			}
		or option 2:
			for each Box {
				move Stack from BoxN to Box(N-1);
			}
	}