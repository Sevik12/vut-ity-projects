# Author: Dominik Harmim <xharmi00@stud.fit.vutbr.cz>

PROJ=proj5
PACK=xharmi00-fit
IMAGES_DIRECTORY=./img

.PHONY: pdflatex pack clean

$(PROJ).pdf: $(PROJ).ps
	ps2pdf $^


$(PROJ).ps: $(PROJ).dvi
	dvips $^


$(PROJ).dvi: $(PROJ).tex
	latex $^
	latex $^


pdflatex: $(PROJ).tex
	pdflatex $^
	pdflatex $^


pack: clean $(PACK).tar.gz


$(PACK).tar.gz: $(PROJ).tex $(IMAGES_DIRECTORY)
	tar -czf $@ $^ Makefile


clean:
	rm -f $(PROJ).aux $(PROJ).dvi $(PROJ).log $(PROJ).ps\
	 $(PROJ).synctex.gz $(PROJ).fls $(PROJ).fdb_latexmk $(PROJ).nav\
	 $(PROJ).out $(PROJ).snm $(PROJ).toc $(PROJ).vrb $(wildcard $(IMAGES_DIRECTORY)/*-eps-converted-to.pdf)
