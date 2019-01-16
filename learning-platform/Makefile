OUT+= 	introduction.html
OUT+= 	foundations-usability.html


.PHONY: all
all: ${OUT}


foundations.tex: ../modules/foundations/overview/abstract.tex
usability.tex: ../modules/usability/overview/abstract.tex

foundations-usability.html: foundations-usability.tex
	pandoc -s $< -o $@ --bibliography foundations-usability.bib

foundations-usability.html: foundations.tex usability.tex
foundations-usability.html: foundations-usability.bib

foundations-usability.bib: ../modules/foundations/overview/overview.bib
foundations-usability.bib: ../modules/usability/overview/overview.bib

foundations.tex usability.tex foundations-usability.bib:
	cat $^ > $@


.PHONY: clean
clean:
	${RM} ${OUT}
	${RM} foundations-usability.html
	${RM} foundations.tex usability.tex foundations-usability.bib


INCLUDE_MAKEFILES?=../makefiles
include ${INCLUDE_MAKEFILES}/doc.mk

