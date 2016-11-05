.SECONDARY:

all: como.pdf

%.pdf: %.tex
	pdflatex $<
	@grep -e 'may have changed' $(basename $<).log && rm $@; $(MAKE) $@ || echo "done."

%.bbl: como.bib %.aux
	bibtex $*

%.aux: %.tex
	pdflatex $*

como.pdf: como.tex como.bbl



.PHONY: clean

clean:
	rm -f *.bbl *.blg *.bak *.dvi *.log *.aux
