# CADT Latex Poster Template

ACET template allows authors to use your favourite software for preparing posters such as Adobe Illustrator, Microsoft PowerPoint. We also prepared a beamer poster style latex template (default to A0 size) for the academic/scientific community.  

Based on the oxford-poster (https://github.com/gbaydin/oxford-poster)  
Based on the I6pd2 style created by Thomas Deselaers an Philippe Dreuw.  

Written by Ye Kyaw Thu
Last updated: 25 July 2023  


Updated by Peng Lykheang


## How to Compile and Open the PDF Poster

After you update the source latex (acet_poster.tex) and bibtex (acet_poster.bib) files, type following commands:  

```bash
make
make view
```

## Removing LaTeX buildfiles

When you compile a tex file, you several output files such as .toc (relating to \tableofcontents), .aux (mostly used for reference information), .bbl (used by biblatex). If you want to clean such LaTex buildfiles type follow command:  

```bash
make clean
```

If you want to clean compiled PDF poster and also LaTex buildfiles type following command:  

```bash
make clean_all
```

## Makefile

The source of the Makefile is as follows and update the latex compiler and PDF viewer etc. based on your requirements:  

```
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

```

"#" in a line of a Makefile starts a comment. If you want to switch between portrait and landscape layout, switch comment out following lines of the Makefile:  

```
FILENAME=acet_poster_landscape
#FILENAME=acet_poster_portrait
```

## File Information

File information:  

- [acet_poster_portrait.tex](https://github.com/NiptictLab/ACET_2022_templates-/blob/main/poster/acet_poster_portrait.tex) (latex source for portrait layout)
- [acet_poster_landscape.tex](https://github.com/NiptictLab/ACET_2022_templates-/blob/main/poster/acet_poster_landscape.tex) (latex source for landscape layout)
- [beamerthemeACET.sty](https://github.com/NiptictLab/ACET_2022_templates-/blob/main/poster/beamerthemeACET.sty) (modified version of Oxford style file)
- [acet_poster.bib](https://github.com/NiptictLab/ACET_2022_templates-/blob/main/poster/acet_poster.bib) (BibTex file for citations)
- [Makefile](https://github.com/NiptictLab/ACET_2022_templates-/blob/main/poster/Makefile) (make utility for automation of the latex compilation)
- [fig/](https://github.com/NiptictLab/ACET_2022_templates-/tree/main/poster/fig) (a folder for figures)
- [acet_poster_portrait.pdf](https://github.com/NiptictLab/ACET_2022_templates-/blob/main/poster/acet_poster_portrait.pdf) (compiled portrait PDF poster file)  
- [acet_poster_landscape.pdf](https://github.com/NiptictLab/ACET_2022_templates-/blob/main/poster/acet_poster_landscape.pdf) (compiled landscape PDF poster file)  

## Reference

https://mirror.kku.ac.th/CTAN/macros/latex/contrib/beamer/doc/beameruserguide.pdf  
https://www.r-bloggers.com/2011/11/create-your-own-beamer-template/  
https://www.overleaf.com/learn/latex/Posters  
https://github.com/deselaers/latex-beamerposter  
https://github.com/deselaers/latex-beamerposter/blob/master/themes/beamerthemeI6pd2.sty  

