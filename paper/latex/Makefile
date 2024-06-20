# Makefile for ACET 2022 Paper Template
# Written by Ye Kyaw Thu, Affiliate Professor, CADT, Cambodia
# Last updated: 29 June 2022

.PHONY: all clean view

FILE=acet

all: $(FILE).pdf

clean:
	rm $(FILE).pdf *.aux *.log #*.blg *.bbl

view:
	evince $(FILE).pdf
	#qpdfview $(FILE).pdf

$(FILE).pdf: $(FILE).tex
	xelatex $(FILE).tex
	xelatex $(FILE).tex
	bibtex $(FILE)
	xelatex $(FILE).tex
	evince $(FILE).pdf
