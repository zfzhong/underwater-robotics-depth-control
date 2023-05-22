SHELL=/bin/bash
OUTFILE=design-doc

.SUFFIXES:
.SUFFIXES: .bib .pdf .tex
.PHONY: clean

run: $(OUTFILE).pdf

$(OUTFILE).pdf:	$(OUTFILE).bbl $(OUTFILE).tex
	pdflatex $(OUTFILE).tex -draftmode
	pdflatex $(OUTFILE).tex

$(OUTFILE).bbl:	$(OUTFILE).aux
	bibtex $(OUTFILE).aux

$(OUTFILE).aux:	reference.bib
	pdflatex $(OUTFILE).tex -draftmode
	pdflatex $(OUTFILE).tex -draftmode

clean:
	rm *.aux *.bbl *.blg *.log *.out *.pdf *.pre *.gz
