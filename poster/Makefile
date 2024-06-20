# Makefile for ACET 2022 Poster Template
# Written by Ye Kyaw Thu, Affiliate Professor, CADT, Cambodia
# Last updated: 29 June 2022

.PHONY: all old view clean clean_all

LATEX=pdflatex
BIBTEX=bibtex
FILENAME=acet_poster_landscape
#FILENAME=acet_poster_portrait
SOURCES=$(FILENAME).tex

OLD_SOURCES=old.tex
PDF_VIEWER=evince

all:
	$(LATEX) $(SOURCES)
	$(BIBTEX) $(FILENAME)
	$(LATEX) $(SOURCES)
	$(LATEX) $(SOURCES)

old:
	$(LATEX) $(OLD_SOURCES)
	$(LATEX) $(OLD_SOURCES)
	$(LATEX) $(OLD_SOURCES)

view:
	$(PDF_VIEWER) $(FILENAME).pdf

clean:
	@rm -vf $(FILENAME).aux $(FILENAME).log $(FILENAME).nav $(FILENAME).out $(FILENAME).snm $(FILENAME).toc $(FILENAME).vrb
	@echo "Removed LaTeX buildfiles."

clean_all: clean
	@rm -vf $(FILENAME).pdf
	@echo "Removed PDF."

