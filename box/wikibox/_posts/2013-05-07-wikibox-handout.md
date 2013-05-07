---
layout: post
box: wikibox
title: Handout and Printing
tags: ' #box(wikibox) '
---

For printing a card as pdf or on paper use these **Layout** settings:

## DIN A 4 (foldable)

A standard DIN A 4 paper with 2 columns (4 pages on 1 paper), optional duplex print (8 pages on 1 paper) and folding for distracting-free learning and easy transportation.

1. **Print** form within Marked or Web browser (as PDF or directly to Printer)
2. **Choose Layout**
	- Pages per Sheet: 4
	- Layout Direction: Flipped N 
	  (Picture 3 on Mac = order: top left, bottom left, top right, bottom right)
	- Border: None
3. **Choose Duplex Printing** (optional)
	- Print Area: Use normal-size printing - Stapling Side: Long-Side stapling (Right)
4. **Folding the printed paper** (optional)
	- for focused studying: fold paper on horizontal mid (each column is on own flat surface)
	- for transportation: fold paper again on vertical mid to get a portable DIN A 6 size

## DIN A 6 Booklet

A DIN A 6 booklet out of a folded DIN A 4 paper (4 pages on 1 paper).

1. **Save as Standard Paper (PDF) and Convert to PostScript File (PS)**
	- Pages per Sheet: 1
	- Duplex/Two-Sided: No
	- optional: print directly to pdf.
2. **Run CLI-Script**
	- Sort DIN A 4 pages to book order (**psbook**)
	- Resize pages to DIN A 6 (**pstops**)
	- Merge them together to a DIN A4 paper
	- Convert them to printable pdf file (**ps2pdf**)
3. **Print PDF-File**
	- Pages per Sheet: 1
	- Duplex/Two-Sided: Yes
4. **Fold Paper**
	- Fold and cut paper (Scissor) to fit booklet format.

CLI-Script for DIN A4 Book:

	cat input.ps | psbook > output.ps
	ps2pdf  output.ps  output.pdf

CLI-Script for DIN A6 Booklet:

	cat input.ps | psbook | pstops '1:0@0.5' | pstops '2:0+1(10.5cm,0)' | pstops '4:0(0,14.8cm)+2,1(0,14.8cm)+3' > output.ps
	ps2pdf  output.ps  output.pdf`

Reference:

- [DIN A 6 Booklet](http://www.rootz.de/2010/12/ein-booklet-in-din-a6-als-druckfertige-pdf-datei-erstellen/)