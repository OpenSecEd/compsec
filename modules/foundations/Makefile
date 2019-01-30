OUT+= 	foundations.html

SUBDIR+=security/security
SUBDIR+=security/scientific-method
SUBDIR+=usability/attacking-humans
SUBDIR+=usability/psychology

SUBDIR_GOALS=all clean distclean


.PHONY: all
all: ${OUT}

foundations.md: security/security/README.md
foundations.md: security/scientific-method/README.md
foundations.md:
	${CAT} $^ > $@


.PHONY: all
all: abstract.tex abstract.bib

abstract.tex: security/security/abstract.tex
abstract.tex: security/scientific-method/abstract.tex
abstract.tex: usability/attacking-humans/abstract.tex
abstract.tex: usability/psychology/abstract.tex

abstract.tex:
	${RM} abstract.tex
	echo "\\paragraph{What is security?}" >> abstract.tex
	cat security/security/abstract.tex >> abstract.tex
	echo "\\paragraph{The scientific method}" >> abstract.tex
	cat security/scientific-method/abstract.tex >> abstract.tex
	echo "\\paragraph{Attacking humans}" >> abstract.tex
	cat usability/attacking-humans/abstract.tex >> abstract.tex
	echo "\\paragraph{Psychology}" >> abstract.tex
	cat usability/psychology/abstract.tex >> abstract.tex

abstract.bib: security/security/security.bib
abstract.bib: security/scientific-method/scientific-method.bib
abstract.bib: usability/attacking-humans/attacking-humans.bib
abstract.bib: usability/psychology/psychology.bib

abstract.bib:
	${CAT} $^ > $@


.PHONY: clean
clean:
	${RM} ${OUT}
	${RM} abstract.tex


INCLUDE_MAKEFILES?=../../makefiles
include ${INCLUDE_MAKEFILES}/doc.mk
include ${INCLUDE_MAKEFILES}/subdir.mk

