	thesis_template
	Seth R. Johnson

This is a sample repository for a University of Michigan thesis. For it to
compile, you probably need several extra packages, including `fourier` (in
texlive-fonts-extra). Furthermore, you need to make sure pdflatex uses the included `texmf` directory. On a Mac, the command to do this is:

	cd [blah]/thesis_template
	ln -s $(pwd)/texmf ~/Library/


To compile the thesis, which resides in the `thesis` directory, either use the
(rather fragile) Makefile via the `make` command, or do:

	pdflatex thesis
	bibtex thesis
	pdflatex thesis


I also have the chapters set up as individual documents as well as chapters in
the thesis. This is accomplished via the `thesis/_individual` directory.
TeXShop, as well as `vim` configured with [this script
here](http://reference-man.blogspot.com/2011/09/fully-integrated-latex-in-macvim.html),
will by default compile the individual document, which will run much quicker
than the full-blown thesis.

The included [`umthesis` class](http://www.ctan.org/pkg/umthesis) is written by
Rob Felty. I modified the style file to better handle printing double-sided
dissertations (which may be done when giving copies to professors).
