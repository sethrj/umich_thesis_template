# Yes, this makefile sucks. I know. For a better one (which takes longer and creates lots of auxiliary files and such), see :
# http://code.google.com/p/latex-makefile/
SHELL := /bin/bash

all:
	pdflatex -draftmode -interaction=batchmode thesis 
	bibtex -terse thesis
	pdflatex -interaction=batchmode thesis
	$(if -n $(grep "Rerun to get cross-references right" thesis.log), \
		pdflatex -interaction=batchmode thesis, \
		@echo "No third run necessary")
	@chflags hidden *.aux *.log
	@open -b net.sourceforge.skim-app.skim thesis.pdf
	grep -n Warning thesis.log || echo "No warnings found! Yay!"

clean:
	rm -f *.aux thesis.blg thesis.log thesis.out thesis.bbl thesis.lof \
		     thesis.lot thesis.pdf thesis.toc

.PHONY: all clean

